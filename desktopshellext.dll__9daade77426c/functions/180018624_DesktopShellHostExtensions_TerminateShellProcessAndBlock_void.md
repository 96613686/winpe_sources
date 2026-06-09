# DesktopShellHostExtensions::TerminateShellProcessAndBlock(void *)

- ea: `0x180018624`
- end: `0x180018706`
- name: `?TerminateShellProcessAndBlock@DesktopShellHostExtensions@@AEAAKPEAX@Z`
- size: `226`
- prototype: `unsigned int(DesktopShellHostExtensions *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017f00`

## callees

- `0x180018624`
- `0x18001a18c`
- `0x180024fe8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800186b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800186e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800186b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800186e6`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800186f6`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800186f6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180018673`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180018673`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x180018642`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x180018642`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800186a2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800186a2`

## string_xrefs

- `0x180018652`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x180018682`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x1800186c9`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`

## pseudocode

```c
__int64 __fastcall DesktopShellHostExtensions::TerminateShellProcessAndBlock(
        DesktopShellHostExtensions *this,
        void *a2)
{
  HWND WindowW; // rax
  const char *v4; // r9
  const char *v5; // r9
  DWORD v6; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD ExitCode; // [rsp+30h] [rbp+8h] BYREF
  int v11; // [rsp+34h] [rbp+Ch]

  v11 = HIDWORD(this);
  ExitCode = -1;
  WindowW = FindWindowW(L"Shell_TrayWnd", 0);
  if ( WindowW )
  {
    PostMessageW(WindowW, 0x5B4u, 0, 0);
    v6 = WaitForSingleObjectEx(a2, 0x4E20u, 0);
    if ( !v6 )
    {
      GetExitCodeProcess(a2, &ExitCode);
      return ExitCode;
    }
    if ( v6 != 258 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x14E,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
        v7);
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x138,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
      v4);
  }
  ExitCode = -805306369;
  if ( !TerminateProcess(a2, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x149,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
      v5);
  WaitForSingleObjectEx(a2, 0x4E20u, 0);
  return ExitCode;
}

```

## disassembly

```asm
0x180018624  mov     qword ptr [rsp+ExitCode], rcx
0x180018629  push    rbx
0x18001862a  sub     rsp, 20h
0x18001862e  mov     rbx, rdx
0x180018631  mov     [rsp+28h+ExitCode], 0FFFFFFFFh
0x180018639  xor     edx, edx; lpWindowName
0x18001863b  lea     rcx, ClassName; "Shell_TrayWnd"
0x180018642  call    cs:__imp_FindWindowW
0x180018648  test    rax, rax
0x18001864b  jnz     short loc_180018694
0x18001864d  mov     rcx, [rsp+28h]; this
0x180018652  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x180018659  mov     edx, 138h; void *
0x18001865e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180018663  mov     edx, 1; uExitCode
0x180018668  mov     [rsp+28h+ExitCode], 0CFFFFFFFh
0x180018670  mov     rcx, rbx; hProcess
0x180018673  call    cs:__imp_TerminateProcess
0x180018679  test    eax, eax
0x18001867b  jnz     short loc_1800186DB
0x18001867d  mov     rcx, [rsp+28h]; this
0x180018682  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x180018689  mov     edx, 149h; void *
0x18001868e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180018694  xor     r9d, r9d; lParam
0x180018697  xor     r8d, r8d; wParam
0x18001869a  mov     edx, 5B4h; Msg
0x18001869f  mov     rcx, rax; hWnd
0x1800186a2  call    cs:__imp_PostMessageW
0x1800186a8  xor     r8d, r8d; bAlertable
0x1800186ab  mov     edx, 4E20h; dwMilliseconds
0x1800186b0  mov     rcx, rbx; hHandle
0x1800186b3  call    cs:__imp_WaitForSingleObjectEx
0x1800186b9  test    eax, eax
0x1800186bb  jz      short loc_1800186EE
0x1800186bd  cmp     eax, 102h
0x1800186c2  jz      short loc_180018663
0x1800186c4  mov     rcx, [rsp+28h]; this
0x1800186c9  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x1800186d0  mov     edx, 14Eh; void *
0x1800186d5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800186db  xor     r8d, r8d; bAlertable
0x1800186de  mov     edx, 4E20h; dwMilliseconds
0x1800186e3  mov     rcx, rbx; hHandle
0x1800186e6  call    cs:__imp_WaitForSingleObjectEx
0x1800186ec  jmp     short loc_1800186FC
0x1800186ee  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x1800186f3  mov     rcx, rbx; hProcess
0x1800186f6  call    cs:__imp_GetExitCodeProcess
0x1800186fc  mov     eax, [rsp+28h+ExitCode]
0x180018700  add     rsp, 20h
0x180018704  pop     rbx
0x180018705  retn
```

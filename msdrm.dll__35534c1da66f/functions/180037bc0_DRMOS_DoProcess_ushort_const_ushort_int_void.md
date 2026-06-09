# DRMOS::DoProcess(ushort const *,ushort *,int,void *)

- ea: `0x180037bc0`
- end: `0x180037d2f`
- name: `?DoProcess@DRMOS@@YAJPEBGPEAGHPEAX@Z`
- size: `367`
- prototype: `int __fastcall(const WCHAR *this, const unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002cb38`

## callees

- `0x180037bc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037c9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037c9a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180037cbd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180037cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c61`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180037d25`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180037d25`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180037c57`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180037c57`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180037cd2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180037cd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037cdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037ce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037cdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037ce6`

## pseudocode

```c
int __fastcall DRMOS::DoProcess(const WCHAR *this, const unsigned __int16 *a2, unsigned __int16 *a3, void *a4)
{
  int result; // eax
  int v6; // ebx
  DWORD i; // eax
  int v8; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-39h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+78h] [rbp-19h] BYREF
  DWORD ExitCode; // [rsp+108h] [rbp+77h] BYREF

  *(_QWORD *)&StartupInfo.cb = 104;
  ExitCode = 0;
  memset(&StartupInfo.lpReserved, 0, 96);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessW(this, 0, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v6 = 0;
    for ( i = WaitForMultipleObjectsEx(1u, &ProcessInformation.hProcess, 0, 0xFAu, 0);
          i == 258;
          i = WaitForMultipleObjectsEx(1u, &ProcessInformation.hProcess, 0, 0xFAu, 0) )
    {
      if ( ++v6 == 720 )
      {
        v8 = -2147467259;
        goto LABEL_17;
      }
      if ( !WaitForSingleObject(a4, 0) )
      {
        v8 = -2147168447;
LABEL_17:
        TerminateProcess(ProcessInformation.hProcess, 1u);
        return v8;
      }
    }
    GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
    result = ExitCode;
    if ( (int)ExitCode > 0 )
      return (unsigned __int16)ExitCode | 0x80070000;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180037bc0  mov     rax, rsp
0x180037bc3  mov     [rax+8], rbx
0x180037bc7  mov     [rax+10h], rdi
0x180037bcb  mov     [rax+18h], r8d
0x180037bcf  push    rbp
0x180037bd0  lea     rbp, [rax-5Fh]
0x180037bd4  sub     rsp, 0E0h
0x180037bdb  xor     eax, eax
0x180037bdd  mov     qword ptr [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x180037be5  xorps   xmm0, xmm0
0x180037be8  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180037bec  mov     [rbp+57h+ExitCode], eax
0x180037bef  xorps   xmm1, xmm1
0x180037bf2  mov     qword ptr [rbp+57h+StartupInfo.wShowWindow], rax
0x180037bf6  mov     rdi, r9
0x180037bf9  mov     [rbp+57h+StartupInfo.lpReserved], rax
0x180037bfd  xor     r9d, r9d; lpThreadAttributes
0x180037c00  mov     [rbp+57h+StartupInfo.lpReserved2], rax
0x180037c04  xor     r8d, r8d; lpProcessAttributes
0x180037c07  mov     [rbp+57h+StartupInfo.hStdError], rax
0x180037c0b  xor     edx, edx; lpCommandLine
0x180037c0d  lea     rax, [rbp+57h+ProcessInformation]
0x180037c11  movdqa  xmmword ptr [rbp+57h+StartupInfo.lpDesktop], xmm0
0x180037c16  mov     [rsp+0E0h+lpProcessInformation], rax; lpProcessInformation
0x180037c1b  lea     rax, [rbp+57h+StartupInfo]
0x180037c1f  mov     [rsp+0E0h+lpStartupInfo], rax; lpStartupInfo
0x180037c24  mov     [rsp+0E0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180037c2d  mov     [rsp+0E0h+lpEnvironment], 0; lpEnvironment
0x180037c36  mov     [rsp+0E0h+dwCreationFlags], 8000000h; dwCreationFlags
0x180037c3e  mov     [rsp+0E0h+bInheritHandles], 0; bInheritHandles
0x180037c46  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180037c4a  movups  xmmword ptr [rbp+57h+StartupInfo.dwX], xmm1
0x180037c4e  movups  xmmword ptr [rbp+57h+StartupInfo.dwXCountChars], xmm1
0x180037c52  movdqa  xmmword ptr [rbp+57h+StartupInfo.hStdInput], xmm0
0x180037c57  call    cs:__imp_CreateProcessW
0x180037c5d  test    eax, eax
0x180037c5f  jnz     short loc_180037C7F
0x180037c61  call    cs:__imp_GetLastError
0x180037c67  test    eax, eax
0x180037c69  jle     short loc_180037C73
0x180037c6b  movzx   eax, ax
0x180037c6e  or      eax, 80070000h
0x180037c73  test    eax, eax
0x180037c75  mov     ebx, 80004005h
0x180037c7a  cmovns  eax, ebx
0x180037c7d  jmp     short loc_180037CFB
0x180037c7f  xor     ebx, ebx
0x180037c81  mov     [rsp+0E0h+bInheritHandles], ebx
0x180037c85  jmp     short loc_180037CAC
0x180037c87  inc     ebx
0x180037c89  cmp     ebx, 2D0h
0x180037c8f  jz      loc_180037D17
0x180037c95  xor     edx, edx; dwMilliseconds
0x180037c97  mov     rcx, rdi; hHandle
0x180037c9a  call    cs:__imp_WaitForSingleObject
0x180037ca0  test    eax, eax
0x180037ca2  jz      short loc_180037D10
0x180037ca4  mov     [rsp+0E0h+bInheritHandles], 0; bAlertable
0x180037cac  xor     r8d, r8d; bWaitAll
0x180037caf  lea     rdx, [rbp+57h+ProcessInformation]; lpHandles
0x180037cb3  mov     r9d, 0FAh; dwMilliseconds
0x180037cb9  lea     ecx, [r8+1]; nCount
0x180037cbd  call    cs:__imp_WaitForMultipleObjectsEx
0x180037cc3  cmp     eax, 102h
0x180037cc8  jz      short loc_180037C87
0x180037cca  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x180037cce  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x180037cd2  call    cs:__imp_GetExitCodeProcess
0x180037cd8  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x180037cdc  call    cs:__imp_CloseHandle
0x180037ce2  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180037ce6  call    cs:__imp_CloseHandle
0x180037cec  mov     eax, [rbp+57h+ExitCode]
0x180037cef  test    eax, eax
0x180037cf1  jle     short loc_180037CFB
0x180037cf3  movzx   eax, ax
0x180037cf6  or      eax, 80070000h
0x180037cfb  lea     r11, [rsp+0E0h+var_s0]
0x180037d03  mov     rbx, [r11+10h]
0x180037d07  mov     rdi, [r11+18h]
0x180037d0b  mov     rsp, r11
0x180037d0e  pop     rbp
0x180037d0f  retn
0x180037d10  mov     ebx, 8004CF41h
0x180037d15  jmp     short loc_180037D1C
0x180037d17  mov     ebx, 80004005h
0x180037d1c  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x180037d20  mov     edx, 1; uExitCode
0x180037d25  call    cs:__imp_TerminateProcess
0x180037d2b  mov     eax, ebx
0x180037d2d  jmp     short loc_180037CFB
```

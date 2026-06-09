# ImpersonatingCreateProcess(ushort *,ushort *,int)

- ea: `0x18002afa8`
- end: `0x18002b1a3`
- name: `?ImpersonatingCreateProcess@@YAJPEAG0H@Z`
- size: `507`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007604`

## callees

- `0x18002afa8`
- `0x18005583a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b126`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b126`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002b024`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002b024`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002b06b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002b076`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002b06b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002b076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b13e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b16e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b17d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b13e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b16e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b17d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18002b115`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18002b115`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b04c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b04c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b034`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002b134`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002b134`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002b0a9`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002b0a9`

## pseudocode

```c
__int64 __fastcall ImpersonatingCreateProcess(LPCWSTR lpApplicationName, LPWSTR lpCommandLine)
{
  int v4; // ebx
  HANDLE CurrentThread; // rax
  signed int v6; // eax
  signed int LastError; // eax
  int v8; // ebx
  __int64 result; // rax
  HANDLE hToken; // [rsp+60h] [rbp-49h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-41h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-29h] BYREF
  DWORD ExitCode; // [rsp+120h] [rbp+77h] BYREF
  void *TokenHandle; // [rsp+128h] [rbp+7Fh] BYREF

  ExitCode = 0;
  TokenHandle = 0;
  hToken = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = (LPWSTR)&Password;
  StartupInfo.lpReserved = 0;
  StartupInfo.lpTitle = 0;
  StartupInfo.dwFlags = 129;
  *(_DWORD *)&StartupInfo.wShowWindow = 6;
  StartupInfo.lpReserved2 = 0;
  v4 = CoImpersonateClient();
  if ( v4 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      v4 = CoRevertToSelf();
      if ( v4 < 0 )
        goto LABEL_16;
      if ( DuplicateTokenEx(TokenHandle, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, &hToken)
        && CreateProcessAsUserW(
             hToken,
             lpApplicationName,
             lpCommandLine,
             0,
             0,
             0,
             8u,
             0,
             0,
             &StartupInfo,
             &ProcessInformation) )
      {
        WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
        GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
        if ( !ExitCode )
          goto LABEL_16;
        if ( (int)ExitCode <= 0 )
        {
          v4 = ExitCode;
          goto LABEL_16;
        }
        v8 = (unsigned __int16)ExitCode;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError <= 0 )
          goto LABEL_16;
        v8 = (unsigned __int16)LastError;
      }
      v4 = v8 | 0x80070000;
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      CoRevertToSelf();
    }
  }
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( hToken )
    CloseHandle(hToken);
  if ( v4 )
    return (unsigned int)v4;
  result = ExitCode;
  if ( !ExitCode )
    return (unsigned int)v4;
  return result;
}

```

## disassembly

```asm
0x18002afa8  mov     [rsp-8+arg_0], rbx
0x18002afad  mov     [rsp-8+ExitCode], r8d
0x18002afb2  push    rbp
0x18002afb3  push    rsi
0x18002afb4  push    rdi
0x18002afb5  lea     rbp, [rsp-47h]
0x18002afba  sub     rsp, 0F0h
0x18002afc1  xor     eax, eax
0x18002afc3  mov     rdi, rdx
0x18002afc6  mov     rsi, rcx
0x18002afc9  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18002afcd  xorps   xmm0, xmm0
0x18002afd0  mov     [rbp+57h+ExitCode], eax
0x18002afd3  xor     edx, edx; Val
0x18002afd5  mov     [rbp+57h+TokenHandle], rax
0x18002afd9  lea     ebx, [rax+68h]
0x18002afdc  mov     [rbp+57h+hToken], rax
0x18002afe0  mov     r8d, ebx; Size
0x18002afe3  lea     rcx, [rbp+57h+StartupInfo]; void *
0x18002afe7  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18002afeb  call    memset_0
0x18002aff0  lea     rax, Password
0x18002aff7  mov     [rbp+57h+StartupInfo.cb], ebx
0x18002affa  mov     [rbp+57h+StartupInfo.lpDesktop], rax
0x18002affe  mov     [rbp+57h+StartupInfo.lpReserved], 0
0x18002b006  mov     [rbp+57h+StartupInfo.lpTitle], 0
0x18002b00e  mov     [rbp+57h+StartupInfo.dwFlags], 81h
0x18002b015  mov     dword ptr [rbp+57h+StartupInfo.wShowWindow], 6
0x18002b01c  mov     [rbp+57h+StartupInfo.lpReserved2], 0
0x18002b024  call    cs:__imp_CoImpersonateClient
0x18002b02a  mov     ebx, eax
0x18002b02c  test    eax, eax
0x18002b02e  js      loc_18002B165
0x18002b034  call    cs:__imp_GetCurrentThread
0x18002b03a  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002b03e  mov     edx, 0F01FFh; DesiredAccess
0x18002b043  mov     rcx, rax; ThreadHandle
0x18002b046  mov     r8d, 1; OpenAsSelf
0x18002b04c  call    cs:__imp_OpenThreadToken
0x18002b052  test    eax, eax
0x18002b054  jnz     short loc_18002B076
0x18002b056  call    cs:__imp_GetLastError
0x18002b05c  mov     ebx, eax
0x18002b05e  test    eax, eax
0x18002b060  jle     short loc_18002B06B
0x18002b062  movzx   ebx, ax
0x18002b065  or      ebx, 80070000h
0x18002b06b  call    cs:__imp_CoRevertToSelf
0x18002b071  jmp     loc_18002B165
0x18002b076  call    cs:__imp_CoRevertToSelf
0x18002b07c  mov     ebx, eax
0x18002b07e  test    eax, eax
0x18002b080  js      loc_18002B165
0x18002b086  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x18002b08a  lea     rax, [rbp+57h+hToken]
0x18002b08e  mov     [rsp+100h+phNewToken], rax; phNewToken
0x18002b093  mov     r9d, 2; ImpersonationLevel
0x18002b099  xor     r8d, r8d; lpTokenAttributes
0x18002b09c  mov     [rsp+100h+TokenType], 1; TokenType
0x18002b0a4  mov     edx, 0F01FFh; dwDesiredAccess
0x18002b0a9  call    cs:__imp_DuplicateTokenEx
0x18002b0af  test    eax, eax
0x18002b0b1  jnz     short loc_18002B0CB
0x18002b0b3  call    cs:__imp_GetLastError
0x18002b0b9  mov     ebx, eax
0x18002b0bb  test    eax, eax
0x18002b0bd  jle     loc_18002B165
0x18002b0c3  movzx   ebx, ax
0x18002b0c6  jmp     loc_18002B15F
0x18002b0cb  mov     rcx, [rbp+57h+hToken]; hToken
0x18002b0cf  lea     rax, [rbp+57h+ProcessInformation]
0x18002b0d3  mov     [rsp+100h+lpProcessInformation], rax; lpProcessInformation
0x18002b0d8  xor     r9d, r9d; lpProcessAttributes
0x18002b0db  lea     rax, [rbp+57h+StartupInfo]
0x18002b0df  mov     r8, rdi; lpCommandLine
0x18002b0e2  mov     [rsp+100h+lpStartupInfo], rax; lpStartupInfo
0x18002b0e7  mov     rdx, rsi; lpApplicationName
0x18002b0ea  mov     [rsp+100h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002b0f3  mov     [rsp+100h+lpEnvironment], 0; lpEnvironment
0x18002b0fc  mov     [rsp+100h+dwCreationFlags], 8; dwCreationFlags
0x18002b104  mov     dword ptr [rsp+100h+phNewToken], 0; bInheritHandles
0x18002b10c  mov     qword ptr [rsp+100h+TokenType], 0; lpThreadAttributes
0x18002b115  call    cs:__imp_CreateProcessAsUserW
0x18002b11b  test    eax, eax
0x18002b11d  jz      short loc_18002B0B3
0x18002b11f  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x18002b123  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b126  call    cs:__imp_WaitForSingleObject
0x18002b12c  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x18002b130  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x18002b134  call    cs:__imp_GetExitCodeProcess
0x18002b13a  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18002b13e  call    cs:__imp_CloseHandle
0x18002b144  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18002b148  call    cs:__imp_CloseHandle
0x18002b14e  mov     eax, [rbp+57h+ExitCode]
0x18002b151  test    eax, eax
0x18002b153  jz      short loc_18002B165
0x18002b155  jg      short loc_18002B15B
0x18002b157  mov     ebx, eax
0x18002b159  jmp     short loc_18002B165
0x18002b15b  movzx   ebx, word ptr [rbp+57h+ExitCode]
0x18002b15f  or      ebx, 80070000h
0x18002b165  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002b169  test    rcx, rcx
0x18002b16c  jz      short loc_18002B174
0x18002b16e  call    cs:__imp_CloseHandle
0x18002b174  mov     rcx, [rbp+57h+hToken]; hObject
0x18002b178  test    rcx, rcx
0x18002b17b  jz      short loc_18002B183
0x18002b17d  call    cs:__imp_CloseHandle
0x18002b183  test    ebx, ebx
0x18002b185  jnz     short loc_18002B18E
0x18002b187  mov     eax, [rbp+57h+ExitCode]
0x18002b18a  test    eax, eax
0x18002b18c  jnz     short loc_18002B190
0x18002b18e  mov     eax, ebx
0x18002b190  mov     rbx, [rsp+100h+arg_0]
0x18002b198  add     rsp, 0F0h
0x18002b19f  pop     rdi
0x18002b1a0  pop     rsi
0x18002b1a1  pop     rbp
0x18002b1a2  retn
```

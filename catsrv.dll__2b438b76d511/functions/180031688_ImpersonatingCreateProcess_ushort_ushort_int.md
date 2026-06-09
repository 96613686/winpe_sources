# ImpersonatingCreateProcess(ushort *,ushort *,int)

- ea: `0x180031688`
- end: `0x180031883`
- name: `?ImpersonatingCreateProcess@@YAJPEAG0H@Z`
- size: `507`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a654`

## callees

- `0x180031688`
- `0x18005551a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031806`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031806`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003181e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003184e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003185d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003181e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003184e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003185d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031793`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003172c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003172c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180031814`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180031814`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800317f5`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800317f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031714`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031714`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031789`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031789`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003174b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180031756`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003174b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180031756`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180031704`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180031704`

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
  StartupInfo.lpDesktop = (LPWSTR)&word_18005C890;
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
0x180031688  mov     [rsp-8+arg_0], rbx
0x18003168d  mov     [rsp-8+ExitCode], r8d
0x180031692  push    rbp
0x180031693  push    rsi
0x180031694  push    rdi
0x180031695  lea     rbp, [rsp-47h]
0x18003169a  sub     rsp, 0F0h
0x1800316a1  xor     eax, eax
0x1800316a3  mov     rdi, rdx
0x1800316a6  mov     rsi, rcx
0x1800316a9  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x1800316ad  xorps   xmm0, xmm0
0x1800316b0  mov     [rbp+57h+ExitCode], eax
0x1800316b3  xor     edx, edx; Val
0x1800316b5  mov     [rbp+57h+TokenHandle], rax
0x1800316b9  lea     ebx, [rax+68h]
0x1800316bc  mov     [rbp+57h+hToken], rax
0x1800316c0  mov     r8d, ebx; Size
0x1800316c3  lea     rcx, [rbp+57h+StartupInfo]; void *
0x1800316c7  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x1800316cb  call    memset_0
0x1800316d0  lea     rax, word_18005C890
0x1800316d7  mov     [rbp+57h+StartupInfo.cb], ebx
0x1800316da  mov     [rbp+57h+StartupInfo.lpDesktop], rax
0x1800316de  mov     [rbp+57h+StartupInfo.lpReserved], 0
0x1800316e6  mov     [rbp+57h+StartupInfo.lpTitle], 0
0x1800316ee  mov     [rbp+57h+StartupInfo.dwFlags], 81h
0x1800316f5  mov     dword ptr [rbp+57h+StartupInfo.wShowWindow], 6
0x1800316fc  mov     [rbp+57h+StartupInfo.lpReserved2], 0
0x180031704  call    cs:__imp_CoImpersonateClient
0x18003170a  mov     ebx, eax
0x18003170c  test    eax, eax
0x18003170e  js      loc_180031845
0x180031714  call    cs:__imp_GetCurrentThread
0x18003171a  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003171e  mov     edx, 0F01FFh; DesiredAccess
0x180031723  mov     rcx, rax; ThreadHandle
0x180031726  mov     r8d, 1; OpenAsSelf
0x18003172c  call    cs:__imp_OpenThreadToken
0x180031732  test    eax, eax
0x180031734  jnz     short loc_180031756
0x180031736  call    cs:__imp_GetLastError
0x18003173c  mov     ebx, eax
0x18003173e  test    eax, eax
0x180031740  jle     short loc_18003174B
0x180031742  movzx   ebx, ax
0x180031745  or      ebx, 80070000h
0x18003174b  call    cs:__imp_CoRevertToSelf
0x180031751  jmp     loc_180031845
0x180031756  call    cs:__imp_CoRevertToSelf
0x18003175c  mov     ebx, eax
0x18003175e  test    eax, eax
0x180031760  js      loc_180031845
0x180031766  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x18003176a  lea     rax, [rbp+57h+hToken]
0x18003176e  mov     [rsp+100h+phNewToken], rax; phNewToken
0x180031773  mov     r9d, 2; ImpersonationLevel
0x180031779  xor     r8d, r8d; lpTokenAttributes
0x18003177c  mov     [rsp+100h+TokenType], 1; TokenType
0x180031784  mov     edx, 0F01FFh; dwDesiredAccess
0x180031789  call    cs:__imp_DuplicateTokenEx
0x18003178f  test    eax, eax
0x180031791  jnz     short loc_1800317AB
0x180031793  call    cs:__imp_GetLastError
0x180031799  mov     ebx, eax
0x18003179b  test    eax, eax
0x18003179d  jle     loc_180031845
0x1800317a3  movzx   ebx, ax
0x1800317a6  jmp     loc_18003183F
0x1800317ab  mov     rcx, [rbp+57h+hToken]; hToken
0x1800317af  lea     rax, [rbp+57h+ProcessInformation]
0x1800317b3  mov     [rsp+100h+lpProcessInformation], rax; lpProcessInformation
0x1800317b8  xor     r9d, r9d; lpProcessAttributes
0x1800317bb  lea     rax, [rbp+57h+StartupInfo]
0x1800317bf  mov     r8, rdi; lpCommandLine
0x1800317c2  mov     [rsp+100h+lpStartupInfo], rax; lpStartupInfo
0x1800317c7  mov     rdx, rsi; lpApplicationName
0x1800317ca  mov     [rsp+100h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800317d3  mov     [rsp+100h+lpEnvironment], 0; lpEnvironment
0x1800317dc  mov     [rsp+100h+dwCreationFlags], 8; dwCreationFlags
0x1800317e4  mov     dword ptr [rsp+100h+phNewToken], 0; bInheritHandles
0x1800317ec  mov     qword ptr [rsp+100h+TokenType], 0; lpThreadAttributes
0x1800317f5  call    cs:__imp_CreateProcessAsUserW
0x1800317fb  test    eax, eax
0x1800317fd  jz      short loc_180031793
0x1800317ff  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x180031803  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180031806  call    cs:__imp_WaitForSingleObject
0x18003180c  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x180031810  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x180031814  call    cs:__imp_GetExitCodeProcess
0x18003181a  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18003181e  call    cs:__imp_CloseHandle
0x180031824  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180031828  call    cs:__imp_CloseHandle
0x18003182e  mov     eax, [rbp+57h+ExitCode]
0x180031831  test    eax, eax
0x180031833  jz      short loc_180031845
0x180031835  jg      short loc_18003183B
0x180031837  mov     ebx, eax
0x180031839  jmp     short loc_180031845
0x18003183b  movzx   ebx, word ptr [rbp+57h+ExitCode]
0x18003183f  or      ebx, 80070000h
0x180031845  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180031849  test    rcx, rcx
0x18003184c  jz      short loc_180031854
0x18003184e  call    cs:__imp_CloseHandle
0x180031854  mov     rcx, [rbp+57h+hToken]; hObject
0x180031858  test    rcx, rcx
0x18003185b  jz      short loc_180031863
0x18003185d  call    cs:__imp_CloseHandle
0x180031863  test    ebx, ebx
0x180031865  jnz     short loc_18003186E
0x180031867  mov     eax, [rbp+57h+ExitCode]
0x18003186a  test    eax, eax
0x18003186c  jnz     short loc_180031870
0x18003186e  mov     eax, ebx
0x180031870  mov     rbx, [rsp+100h+arg_0]
0x180031878  add     rsp, 0F0h
0x18003187f  pop     rdi
0x180031880  pop     rsi
0x180031881  pop     rbp
0x180031882  retn
```

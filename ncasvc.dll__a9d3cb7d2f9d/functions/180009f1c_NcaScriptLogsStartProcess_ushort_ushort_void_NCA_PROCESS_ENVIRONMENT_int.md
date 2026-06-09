# NcaScriptLogsStartProcess(ushort *,ushort *,void *,NCA_PROCESS_ENVIRONMENT_ *,int *)

- ea: `0x180009f1c`
- end: `0x18000a390`
- name: `?NcaScriptLogsStartProcess@@YAKPEAG0PEAXPEAUNCA_PROCESS_ENVIRONMENT_@@PEAH@Z`
- size: `1140`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine, HANDLE Token, void **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009ce0`

## callees

- `0x180004f34`
- `0x180009158`
- `0x180009f1c`
- `0x180018fd4`
- `0x18001cc3e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a02c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a07d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a02c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a07d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a329`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000a229`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000a229`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a27c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a27c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000a100`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000a100`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000a318`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000a318`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a01c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a01c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a19a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a19a`
- `USERENV!DestroyEnvironmentBlock` at `0x18000a14d`
- `USERENV!DestroyEnvironmentBlock` at `0x18000a14d`
- `USERENV!CreateEnvironmentBlock` at `0x18000a06d`
- `USERENV!CreateEnvironmentBlock` at `0x18000a06d`
- `KERNEL32!AssignProcessToJobObject` at `0x18000a2cf`
- `KERNEL32!AssignProcessToJobObject` at `0x18000a2cf`

## pseudocode

```c
__int64 __fastcall NcaScriptLogsStartProcess(
        LPCWSTR lpApplicationName,
        LPWSTR lpCommandLine,
        HANDLE Token,
        void **a4,
        int *a5)
{
  unsigned int TempFile; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int *v13; // rsi
  BOOL v14; // eax
  HANDLE hThread; // rcx
  HANDLE hToken; // [rsp+60h] [rbp-61h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-41h] BYREF
  LPVOID Environment; // [rsp+138h] [rbp+77h] BYREF

  hToken = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  Environment = 0;
  TempFile = NcaScriptLogsCreateTempFile(a4 + 1);
  v10 = TempFile;
  if ( TempFile )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 39;
LABEL_45:
      WPP_SF_d(v11[2], v12, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, TempFile);
      goto LABEL_46;
    }
    goto LABEL_46;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v13 = a5;
  StartupInfo.wShowWindow = 0;
  StartupInfo.hStdOutput = a4[1];
  StartupInfo.hStdError = StartupInfo.hStdOutput;
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 257;
  if ( !Token )
    goto LABEL_28;
  if ( a5 )
  {
    if ( !RevertToSelf() )
    {
      TempFile = GetLastError();
      v10 = TempFile;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 44;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    *v13 = 0;
LABEL_28:
    if ( !CreateProcessW(lpApplicationName, lpCommandLine, 0, 0, 1, 4u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      TempFile = GetLastError();
      v10 = TempFile;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 45;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    if ( Token )
    {
      v14 = SetThreadToken(0, Token);
      *v13 = v14;
      if ( !v14 )
      {
        TempFile = GetLastError();
        v10 = TempFile;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 46;
          goto LABEL_45;
        }
        goto LABEL_46;
      }
    }
    goto LABEL_37;
  }
  if ( DuplicateTokenEx(Token, 0xBu, 0, SecurityImpersonation, TokenPrimary, &hToken) )
  {
    if ( !CreateEnvironmentBlock(&Environment, Token, 0) )
    {
      TempFile = GetLastError();
      v10 = TempFile;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 41;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    if ( !CreateProcessAsUserW(
            hToken,
            lpApplicationName,
            lpCommandLine,
            0,
            0,
            1,
            0x404u,
            Environment,
            0,
            &StartupInfo,
            &ProcessInformation) )
    {
      TempFile = GetLastError();
      v10 = TempFile;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 42;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    if ( !DestroyEnvironmentBlock(Environment) )
    {
      TempFile = GetLastError();
      v10 = TempFile;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 43;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
LABEL_37:
    if ( AssignProcessToJobObject(a4[2], ProcessInformation.hProcess) )
    {
      hThread = ProcessInformation.hThread;
      *a4 = ProcessInformation.hProcess;
      if ( ResumeThread(hThread) == -1 )
      {
        TempFile = GetLastError();
        v10 = TempFile;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 48;
          goto LABEL_45;
        }
      }
    }
    else
    {
      TempFile = GetLastError();
      v10 = TempFile;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 47;
        goto LABEL_45;
      }
    }
    goto LABEL_46;
  }
  TempFile = GetLastError();
  v10 = TempFile;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 40;
    goto LABEL_45;
  }
LABEL_46:
  NcaCloseHandle(hToken);
  return v10;
}

```

## disassembly

```asm
0x180009f1c  mov     [rsp-8+arg_0], rbx
0x180009f21  mov     [rsp-8+arg_8], rsi
0x180009f26  push    rbp
0x180009f27  push    rdi
0x180009f28  push    r12
0x180009f2a  push    r14
0x180009f2c  push    r15
0x180009f2e  lea     rbp, [rsp-2Fh]
0x180009f33  sub     rsp, 0F0h
0x180009f3a  xor     eax, eax
0x180009f3c  mov     [rbp+4Fh+hToken], 0
0x180009f44  mov     rdi, r8
0x180009f47  mov     qword ptr [rbp+4Fh+ProcessInformation.dwProcessId], rax
0x180009f4b  mov     r15, rdx
0x180009f4e  mov     r12, rcx
0x180009f51  xorps   xmm0, xmm0
0x180009f54  lea     rcx, [rbp+4Fh+StartupInfo]; void *
0x180009f58  lea     r8d, [rax+68h]; Size
0x180009f5c  xor     edx, edx; Val
0x180009f5e  mov     r14, r9
0x180009f61  movups  xmmword ptr [rbp+4Fh+ProcessInformation.hProcess], xmm0
0x180009f65  call    memset_0
0x180009f6a  lea     rcx, [r14+8]; void **
0x180009f6e  mov     [rbp+4Fh+Environment], 0
0x180009f76  call    ?NcaScriptLogsCreateTempFile@@YAKPEAPEAX@Z; NcaScriptLogsCreateTempFile(void * *)
0x180009f7b  mov     ebx, eax
0x180009f7d  test    eax, eax
0x180009f7f  jz      short loc_180009FAC
0x180009f81  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f88  lea     rdx, WPP_GLOBAL_Control
0x180009f8f  cmp     rcx, rdx
0x180009f92  jz      loc_18000A368
0x180009f98  test    byte ptr [rcx+1Ch], 1
0x180009f9c  jz      loc_18000A368
0x180009fa2  mov     edx, 27h ; '''
0x180009fa7  jmp     loc_18000A355
0x180009fac  xor     eax, eax
0x180009fae  lea     rcx, [rbp+4Fh+StartupInfo]; void *
0x180009fb2  xorps   xmm0, xmm0
0x180009fb5  mov     qword ptr [rbp+4Fh+ProcessInformation.dwProcessId], rax
0x180009fb9  xor     edx, edx; Val
0x180009fbb  movups  xmmword ptr [rbp+4Fh+ProcessInformation.hProcess], xmm0
0x180009fbf  lea     r8d, [rax+68h]; Size
0x180009fc3  call    memset_0
0x180009fc8  mov     rsi, [rbp+4Fh+arg_20]
0x180009fcc  xor     eax, eax
0x180009fce  mov     [rbp+4Fh+StartupInfo.wShowWindow], ax
0x180009fd2  mov     rax, [r14+8]
0x180009fd6  mov     [rbp+4Fh+StartupInfo.hStdOutput], rax
0x180009fda  mov     [rbp+4Fh+StartupInfo.hStdError], rax
0x180009fde  mov     [rbp+4Fh+StartupInfo.cb], 68h ; 'h'
0x180009fe5  mov     [rbp+4Fh+StartupInfo.dwFlags], 101h
0x180009fec  test    rdi, rdi
0x180009fef  jz      loc_18000A1E9
0x180009ff5  test    rsi, rsi
0x180009ff8  jnz     loc_18000A19A
0x180009ffe  lea     rax, [rbp+4Fh+hToken]
0x18000a002  xor     r8d, r8d; lpTokenAttributes
0x18000a005  mov     [rsp+110h+phNewToken], rax; phNewToken
0x18000a00a  lea     r9d, [rsi+2]; ImpersonationLevel
0x18000a00e  lea     edx, [rsi+0Bh]; dwDesiredAccess
0x18000a011  mov     [rsp+110h+TokenType], 1; TokenType
0x18000a019  mov     rcx, rdi; hExistingToken
0x18000a01c  call    cs:__imp_DuplicateTokenEx
0x18000a023  nop     dword ptr [rax+rax+00h]
0x18000a028  test    eax, eax
0x18000a02a  jnz     short loc_18000A063
0x18000a02c  call    cs:__imp_GetLastError
0x18000a033  nop     dword ptr [rax+rax+00h]
0x18000a038  mov     ebx, eax
0x18000a03a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a041  lea     rdx, WPP_GLOBAL_Control
0x18000a048  cmp     rcx, rdx
0x18000a04b  jz      loc_18000A368
0x18000a051  test    byte ptr [rcx+1Ch], 1
0x18000a055  jz      loc_18000A368
0x18000a05b  lea     edx, [rsi+28h]
0x18000a05e  jmp     loc_18000A355
0x18000a063  xor     r8d, r8d; bInherit
0x18000a066  lea     rcx, [rbp+4Fh+Environment]; lpEnvironment
0x18000a06a  mov     rdx, rdi; hToken
0x18000a06d  call    cs:__imp_CreateEnvironmentBlock
0x18000a074  nop     dword ptr [rax+rax+00h]
0x18000a079  test    eax, eax
0x18000a07b  jnz     short loc_18000A0B6
0x18000a07d  call    cs:__imp_GetLastError
0x18000a084  nop     dword ptr [rax+rax+00h]
0x18000a089  mov     ebx, eax
0x18000a08b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a092  lea     rdx, WPP_GLOBAL_Control
0x18000a099  cmp     rcx, rdx
0x18000a09c  jz      loc_18000A368
0x18000a0a2  test    byte ptr [rcx+1Ch], 1
0x18000a0a6  jz      loc_18000A368
0x18000a0ac  mov     edx, 29h ; ')'
0x18000a0b1  jmp     loc_18000A355
0x18000a0b6  mov     rcx, [rbp+4Fh+hToken]; hToken
0x18000a0ba  lea     rax, [rbp+4Fh+ProcessInformation]
0x18000a0be  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x18000a0c3  xor     r9d, r9d; lpProcessAttributes
0x18000a0c6  lea     rax, [rbp+4Fh+StartupInfo]
0x18000a0ca  mov     r8, r15; lpCommandLine
0x18000a0cd  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x18000a0d2  mov     rdx, r12; lpApplicationName
0x18000a0d5  mov     rax, [rbp+4Fh+Environment]
0x18000a0d9  mov     [rsp+110h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000a0e2  mov     [rsp+110h+lpEnvironment], rax; lpEnvironment
0x18000a0e7  mov     [rsp+110h+dwCreationFlags], 404h; dwCreationFlags
0x18000a0ef  mov     dword ptr [rsp+110h+phNewToken], 1; bInheritHandles
0x18000a0f7  mov     qword ptr [rsp+110h+TokenType], 0; lpThreadAttributes
0x18000a100  call    cs:__imp_CreateProcessAsUserW
0x18000a107  nop     dword ptr [rax+rax+00h]
0x18000a10c  test    eax, eax
0x18000a10e  jnz     short loc_18000A149
0x18000a110  call    cs:__imp_GetLastError
0x18000a117  nop     dword ptr [rax+rax+00h]
0x18000a11c  mov     ebx, eax
0x18000a11e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a125  lea     rdx, WPP_GLOBAL_Control
0x18000a12c  cmp     rcx, rdx
0x18000a12f  jz      loc_18000A368
0x18000a135  test    byte ptr [rcx+1Ch], 1
0x18000a139  jz      loc_18000A368
0x18000a13f  mov     edx, 2Ah ; '*'
0x18000a144  jmp     loc_18000A355
0x18000a149  mov     rcx, [rbp+4Fh+Environment]; lpEnvironment
0x18000a14d  call    cs:__imp_DestroyEnvironmentBlock
0x18000a154  nop     dword ptr [rax+rax+00h]
0x18000a159  test    eax, eax
0x18000a15b  jnz     loc_18000A2C7
0x18000a161  call    cs:__imp_GetLastError
0x18000a168  nop     dword ptr [rax+rax+00h]
0x18000a16d  mov     ebx, eax
0x18000a16f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a176  lea     rdx, WPP_GLOBAL_Control
0x18000a17d  cmp     rcx, rdx
0x18000a180  jz      loc_18000A368
0x18000a186  test    byte ptr [rcx+1Ch], 1
0x18000a18a  jz      loc_18000A368
0x18000a190  mov     edx, 2Bh ; '+'
0x18000a195  jmp     loc_18000A355
0x18000a19a  call    cs:__imp_RevertToSelf
0x18000a1a1  nop     dword ptr [rax+rax+00h]
0x18000a1a6  test    eax, eax
0x18000a1a8  jnz     short loc_18000A1E3
0x18000a1aa  call    cs:__imp_GetLastError
0x18000a1b1  nop     dword ptr [rax+rax+00h]
0x18000a1b6  mov     ebx, eax
0x18000a1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1bf  lea     rdx, WPP_GLOBAL_Control
0x18000a1c6  cmp     rcx, rdx
0x18000a1c9  jz      loc_18000A368
0x18000a1cf  test    byte ptr [rcx+1Ch], 1
0x18000a1d3  jz      loc_18000A368
0x18000a1d9  mov     edx, 2Ch ; ','
0x18000a1de  jmp     loc_18000A355
0x18000a1e3  mov     dword ptr [rsi], 0
0x18000a1e9  lea     rax, [rbp+4Fh+ProcessInformation]
0x18000a1ed  xor     r9d, r9d; lpThreadAttributes
0x18000a1f0  mov     [rsp+110h+lpStartupInfo], rax; lpProcessInformation
0x18000a1f5  xor     r8d, r8d; lpProcessAttributes
0x18000a1f8  lea     rax, [rbp+4Fh+StartupInfo]
0x18000a1fc  mov     rdx, r15; lpCommandLine
0x18000a1ff  mov     [rsp+110h+lpCurrentDirectory], rax; lpStartupInfo
0x18000a204  mov     rcx, r12; lpApplicationName
0x18000a207  mov     [rsp+110h+lpEnvironment], 0; lpCurrentDirectory
0x18000a210  mov     qword ptr [rsp+110h+dwCreationFlags], 0; lpEnvironment
0x18000a219  mov     dword ptr [rsp+110h+phNewToken], 4; dwCreationFlags
0x18000a221  mov     [rsp+110h+TokenType], 1; bInheritHandles
0x18000a229  call    cs:__imp_CreateProcessW
0x18000a230  nop     dword ptr [rax+rax+00h]
0x18000a235  test    eax, eax
0x18000a237  jnz     short loc_18000A272
0x18000a239  call    cs:__imp_GetLastError
0x18000a240  nop     dword ptr [rax+rax+00h]
0x18000a245  mov     ebx, eax
0x18000a247  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a24e  lea     rdx, WPP_GLOBAL_Control
0x18000a255  cmp     rcx, rdx
0x18000a258  jz      loc_18000A368
0x18000a25e  test    byte ptr [rcx+1Ch], 1
0x18000a262  jz      loc_18000A368
0x18000a268  mov     edx, 2Dh ; '-'
0x18000a26d  jmp     loc_18000A355
0x18000a272  test    rdi, rdi
0x18000a275  jz      short loc_18000A2C7
0x18000a277  mov     rdx, rdi; Token
0x18000a27a  xor     ecx, ecx; Thread
0x18000a27c  call    cs:__imp_SetThreadToken
0x18000a283  nop     dword ptr [rax+rax+00h]
0x18000a288  mov     [rsi], eax
0x18000a28a  test    eax, eax
0x18000a28c  jnz     short loc_18000A2C7
0x18000a28e  call    cs:__imp_GetLastError
0x18000a295  nop     dword ptr [rax+rax+00h]
0x18000a29a  mov     ebx, eax
0x18000a29c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2a3  lea     rdx, WPP_GLOBAL_Control
0x18000a2aa  cmp     rcx, rdx
0x18000a2ad  jz      loc_18000A368
0x18000a2b3  test    byte ptr [rcx+1Ch], 1
0x18000a2b7  jz      loc_18000A368
0x18000a2bd  mov     edx, 2Eh ; '.'
0x18000a2c2  jmp     loc_18000A355
0x18000a2c7  mov     rdx, [rbp+4Fh+ProcessInformation.hProcess]; hProcess
0x18000a2cb  mov     rcx, [r14+10h]; hJob
0x18000a2cf  call    cs:__imp_AssignProcessToJobObject
0x18000a2d6  nop     dword ptr [rax+rax+00h]
0x18000a2db  test    eax, eax
0x18000a2dd  jnz     short loc_18000A30D
0x18000a2df  call    cs:__imp_GetLastError
0x18000a2e6  nop     dword ptr [rax+rax+00h]
0x18000a2eb  mov     ebx, eax
0x18000a2ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2f4  lea     rdx, WPP_GLOBAL_Control
0x18000a2fb  cmp     rcx, rdx
0x18000a2fe  jz      short loc_18000A368
0x18000a300  test    byte ptr [rcx+1Ch], 1
0x18000a304  jz      short loc_18000A368
0x18000a306  mov     edx, 2Fh ; '/'
0x18000a30b  jmp     short loc_18000A355
0x18000a30d  mov     rax, [rbp+4Fh+ProcessInformation.hProcess]
0x18000a311  mov     rcx, [rbp+4Fh+ProcessInformation.hThread]; hThread
0x18000a315  mov     [r14], rax
0x18000a318  call    cs:__imp_ResumeThread
0x18000a31f  nop     dword ptr [rax+rax+00h]
0x18000a324  cmp     eax, 0FFFFFFFFh
0x18000a327  jnz     short loc_18000A368
0x18000a329  call    cs:__imp_GetLastError
0x18000a330  nop     dword ptr [rax+rax+00h]
0x18000a335  mov     ebx, eax
0x18000a337  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a33e  lea     rdx, WPP_GLOBAL_Control
0x18000a345  cmp     rcx, rdx
0x18000a348  jz      short loc_18000A368
0x18000a34a  test    byte ptr [rcx+1Ch], 1
0x18000a34e  jz      short loc_18000A368
0x18000a350  mov     edx, 30h ; '0'
0x18000a355  mov     rcx, [rcx+10h]
0x18000a359  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000a360  mov     r9d, eax
0x18000a363  call    WPP_SF_d
0x18000a368  mov     rcx, [rbp+4Fh+hToken]
0x18000a36c  call    NcaCloseHandle
0x18000a371  lea     r11, [rsp+110h+var_20]
0x18000a379  mov     eax, ebx
0x18000a37b  mov     rbx, [r11+30h]
0x18000a37f  mov     rsi, [r11+38h]
0x18000a383  mov     rsp, r11
0x18000a386  pop     r15
0x18000a388  pop     r14
0x18000a38a  pop     r12
0x18000a38c  pop     rdi
0x18000a38d  pop     rbp
0x18000a38e  retn
```

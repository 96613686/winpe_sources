# ProcessToken::GetProcessToken(void * *,ulong)

- ea: `0x18019f2d8`
- end: `0x18019f5f9`
- name: `?GetProcessToken@ProcessToken@@QEAAJPEAPEAXK@Z`
- size: `801`
- prototype: `HRESULT __fastcall(ProcessToken *this, void **phProcessToken, unsigned int phProcessToken)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028958`

## callees

- `0x18008db2c`
- `0x1801457c0`
- `0x18014d5f4`
- `0x18019f2d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f3af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f4ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f3af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f4ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019f4d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019f5d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019f4d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019f5d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019f2f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019f4e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019f2f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019f4e2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18019f46a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18019f568`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18019f46a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18019f568`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019f309`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019f4f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019f309`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019f4f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18019f38a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18019f38a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18019f3a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18019f3a1`

## string_xrefs

- `0x18019f366`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18019f3f7`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18019f444`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18019f4b9`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18019f544`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18019f5b7`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x18019f3db`: `Process does not have access to its own token`
- `0x18019f35f`: `ProcessToken::GetProcessToken`
- `0x18019f3f0`: `ProcessToken::GetProcessToken`
- `0x18019f43d`: `ProcessToken::GetProcessToken`
- `0x18019f4b2`: `ProcessToken::GetProcessToken`
- `0x18019f53d`: `ProcessToken::GetProcessToken`
- `0x18019f5b0`: `ProcessToken::GetProcessToken`
- `0x18019f424`: `OpenThreadToken failed: %!WINERROR!`
- `0x18019f499`: `SetThreadToken failed: %!WINERROR!`
- `0x18019f597`: `SetThreadToken failed: %!WINERROR!`
- `0x18019f346`: `OpenProcessToken failed: %!WINERROR!`
- `0x18019f524`: `OpenProcessToken failed: %!WINERROR!`

## pseudocode

```c
__int64 __fastcall ProcessToken::GetProcessToken(ProcessToken *this, void **phProcessToken, unsigned int a3)
{
  signed int v3; // ebx
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  signed int v7; // edi
  HANDLE CurrentThread; // rax
  bool v9; // sf
  HANDLE v10; // rax
  bool v11; // sf
  void *hImpersonationToken; // [rsp+40h] [rbp+8h] BYREF
  void *hProcessToken; // [rsp+48h] [rbp+10h] BYREF

  hImpersonationToken = this;
  v3 = 0;
  hProcessToken = 0;
  *phProcessToken = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &hProcessToken) )
    goto LABEL_51;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError != 5 && LastError != 1346 )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<unsigned int>(
        "onecore\\com\\combase\\processtoken\\processtoken.cxx",
        "ProcessToken::GetProcessToken",
        923,
        ERRORS,
        L"OpenProcessToken failed: %!WINERROR!",
        v7);
    if ( v7 <= 0 )
    {
      v3 = v7;
LABEL_49:
      v9 = v3 < 0;
      goto LABEL_50;
    }
    v3 = (unsigned __int16)v7;
LABEL_24:
    v3 |= 0x80070000;
    goto LABEL_49;
  }
  hImpersonationToken = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &hImpersonationToken) )
  {
    if ( SetThreadToken(0, 0) )
    {
      v10 = GetCurrentProcess();
      if ( OpenProcessToken(v10, 8u, &hProcessToken) )
        goto LABEL_55;
      v3 = GetLastError();
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<unsigned int>(
          "onecore\\com\\combase\\processtoken\\processtoken.cxx",
          "ProcessToken::GetProcessToken",
          904,
          ERRORS,
          L"OpenProcessToken failed: %!WINERROR!",
          v3);
      v11 = v3 < 0;
      if ( v3 > 0 )
      {
        v3 = (unsigned __int16)v3 | 0x80070000;
        v11 = v3 < 0;
      }
      if ( !v11 )
      {
LABEL_55:
        if ( !SetThreadToken(0, hImpersonationToken) )
        {
          v3 = GetLastError();
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            ComTraceMessageT<unsigned int>(
              "onecore\\com\\combase\\processtoken\\processtoken.cxx",
              "ProcessToken::GetProcessToken",
              913,
              ERRORS,
              L"SetThreadToken failed: %!WINERROR!",
              v3);
          if ( v3 > 0 )
            v3 = (unsigned __int16)v3 | 0x80070000;
        }
      }
    }
    else
    {
      v3 = GetLastError();
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<unsigned int>(
          "onecore\\com\\combase\\processtoken\\processtoken.cxx",
          "ProcessToken::GetProcessToken",
          894,
          ERRORS,
          L"SetThreadToken failed: %!WINERROR!",
          v3);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      CloseHandle(hImpersonationToken);
    }
    CloseHandle(hImpersonationToken);
    goto LABEL_49;
  }
  v3 = GetLastError();
  if ( v3 == 1008 )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<>(
        "onecore\\com\\combase\\processtoken\\processtoken.cxx",
        "ProcessToken::GetProcessToken",
        879,
        ERRORS,
        L"Process does not have access to its own token");
    return (unsigned int)-2147024891;
  }
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    ComTraceMessageT<unsigned int>(
      "onecore\\com\\combase\\processtoken\\processtoken.cxx",
      "ProcessToken::GetProcessToken",
      884,
      ERRORS,
      L"OpenThreadToken failed: %!WINERROR!",
      v3);
  v9 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3;
    goto LABEL_24;
  }
LABEL_50:
  if ( !v9 )
LABEL_51:
    *phProcessToken = hProcessToken;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18019f2d8  mov     rax, rsp
0x18019f2db  mov     [rax+18h], rbx
0x18019f2df  mov     [rax+20h], rsi
0x18019f2e3  mov     [rax+8], rcx
0x18019f2e7  push    rdi
0x18019f2e8  sub     rsp, 30h
0x18019f2ec  xor     ebx, ebx
0x18019f2ee  mov     rsi, phProcessToken
0x18019f2f1  mov     [rax+10h], rbx
0x18019f2f5  mov     [phProcessToken], rbx
0x18019f2f8  call    cs:__imp_GetCurrentProcess
0x18019f2fe  mov     rcx, rax; ProcessHandle
0x18019f301  lea     r8, [rsp+38h+hProcessToken]; TokenHandle
0x18019f306  lea     edx, [rbx+8]; DesiredAccess
0x18019f309  call    cs:__imp_OpenProcessToken
0x18019f30f  test    eax, eax
0x18019f311  jnz     loc_18019F5DF
0x18019f317  call    cs:__imp_GetLastError
0x18019f31d  mov     edi, eax
0x18019f31f  cmp     eax, 5
0x18019f322  jz      short loc_18019F385
0x18019f324  cmp     eax, 542h
0x18019f329  jz      short loc_18019F385
0x18019f32b  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x18019f331  test    ecx, ecx
0x18019f333  jnz     short loc_18019F346
0x18019f335  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18019f33b  jz      short loc_18019F372
0x18019f33d  call    IsWppLevelEnabled
0x18019f342  test    al, al
0x18019f344  jz      short loc_18019F372
0x18019f346  lea     rax, aOpenprocesstok; "OpenProcessToken failed: %!WINERROR!"
0x18019f34d  mov     [rsp+38h+var_10], edi; <args_0>
0x18019f351  xor     r9d, r9d; level
0x18019f354  mov     [rsp+38h+format], rax; format
0x18019f359  mov     r8d, 39Bh; line
0x18019f35f  lea     phProcessToken, aProcesstokenGe_0; "ProcessToken::GetProcessToken"
0x18019f366  lea     rcx, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x18019f36d  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18019f372  test    edi, edi
0x18019f374  jg      short loc_18019F37D
0x18019f376  mov     ebx, edi
0x18019f378  jmp     loc_18019F5DB
0x18019f37d  movzx   ebx, di
0x18019f380  jmp     loc_18019F45B
0x18019f385  mov     [rsp+38h+hImpersonationToken], rbx
0x18019f38a  call    cs:__imp_GetCurrentThread
0x18019f390  mov     edx, 4; DesiredAccess
0x18019f395  lea     r9, [rsp+38h+hImpersonationToken]; TokenHandle
0x18019f39a  mov     rcx, rax; ThreadHandle
0x18019f39d  lea     r8d, [phProcessToken-3]; OpenAsSelf
0x18019f3a1  call    cs:__imp_OpenThreadToken
0x18019f3a7  test    eax, eax
0x18019f3a9  jnz     loc_18019F466
0x18019f3af  call    cs:__imp_GetLastError
0x18019f3b5  mov     ebx, eax
0x18019f3b7  cmp     eax, 3F0h
0x18019f3bc  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18019f3c2  jnz     short loc_18019F40D
0x18019f3c4  test    eax, eax
0x18019f3c6  jnz     short loc_18019F3DB
0x18019f3c8  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18019f3ce  jz      short loc_18019F403
0x18019f3d0  xor     ecx, ecx; level
0x18019f3d2  call    IsWppLevelEnabled
0x18019f3d7  test    al, al
0x18019f3d9  jz      short loc_18019F403
0x18019f3db  lea     rax, aProcessDoesNot_0; "Process does not have access to its own"...
0x18019f3e2  xor     r9d, r9d; level
0x18019f3e5  mov     r8d, 36Fh; line
0x18019f3eb  mov     [rsp+38h+format], rax; format
0x18019f3f0  lea     phProcessToken, aProcesstokenGe_0; "ProcessToken::GetProcessToken"
0x18019f3f7  lea     rcx, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x18019f3fe  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18019f403  mov     ebx, 80070005h
0x18019f408  jmp     loc_18019F5E7
0x18019f40d  test    eax, eax
0x18019f40f  jnz     short loc_18019F424
0x18019f411  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18019f417  jz      short loc_18019F450
0x18019f419  xor     ecx, ecx; level
0x18019f41b  call    IsWppLevelEnabled
0x18019f420  test    al, al
0x18019f422  jz      short loc_18019F450
0x18019f424  lea     rax, aOpenthreadtoke_0; "OpenThreadToken failed: %!WINERROR!"
0x18019f42b  mov     [rsp+38h+var_10], ebx; <args_0>
0x18019f42f  xor     r9d, r9d; level
0x18019f432  mov     [rsp+38h+format], rax; format
0x18019f437  mov     r8d, 374h; line
0x18019f43d  lea     phProcessToken, aProcesstokenGe_0; "ProcessToken::GetProcessToken"
0x18019f444  lea     rcx, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x18019f44b  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18019f450  test    ebx, ebx
0x18019f452  jle     loc_18019F5DD
0x18019f458  movzx   ebx, bx
0x18019f45b  or      ebx, 80070000h
0x18019f461  jmp     loc_18019F5DB
0x18019f466  xor     edx, edx; Token
0x18019f468  xor     ecx, ecx; Thread
0x18019f46a  call    cs:__imp_SetThreadToken
0x18019f470  test    eax, eax
0x18019f472  jnz     short loc_18019F4E2
0x18019f474  call    cs:__imp_GetLastError
0x18019f47a  mov     ebx, eax
0x18019f47c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18019f482  test    eax, eax
0x18019f484  jnz     short loc_18019F499
0x18019f486  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18019f48c  jz      short loc_18019F4C5
0x18019f48e  xor     ecx, ecx; level
0x18019f490  call    IsWppLevelEnabled
0x18019f495  test    al, al
0x18019f497  jz      short loc_18019F4C5
0x18019f499  lea     rax, aSetthreadtoken; "SetThreadToken failed: %!WINERROR!"
0x18019f4a0  mov     [rsp+38h+var_10], ebx; <args_0>
0x18019f4a4  xor     r9d, r9d; level
0x18019f4a7  mov     [rsp+38h+format], rax; format
0x18019f4ac  mov     r8d, 37Eh; line
0x18019f4b2  lea     phProcessToken, aProcesstokenGe_0; "ProcessToken::GetProcessToken"
0x18019f4b9  lea     rcx, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x18019f4c0  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18019f4c5  test    ebx, ebx
0x18019f4c7  jle     short loc_18019F4D2
0x18019f4c9  movzx   ebx, bx
0x18019f4cc  or      ebx, 80070000h
0x18019f4d2  mov     rcx, [rsp+38h+hImpersonationToken]; hObject
0x18019f4d7  call    cs:__imp_CloseHandle
0x18019f4dd  jmp     loc_18019F5D0
0x18019f4e2  call    cs:__imp_GetCurrentProcess
0x18019f4e8  lea     r8, [rsp+38h+hProcessToken]; TokenHandle
0x18019f4ed  mov     edx, 8; DesiredAccess
0x18019f4f2  mov     rcx, rax; ProcessHandle
0x18019f4f5  call    cs:__imp_OpenProcessToken
0x18019f4fb  test    eax, eax
0x18019f4fd  jnz     short loc_18019F561
0x18019f4ff  call    cs:__imp_GetLastError
0x18019f505  mov     ebx, eax
0x18019f507  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18019f50d  test    eax, eax
0x18019f50f  jnz     short loc_18019F524
0x18019f511  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18019f517  jz      short loc_18019F550
0x18019f519  xor     ecx, ecx; level
0x18019f51b  call    IsWppLevelEnabled
0x18019f520  test    al, al
0x18019f522  jz      short loc_18019F550
0x18019f524  lea     rax, aOpenprocesstok; "OpenProcessToken failed: %!WINERROR!"
0x18019f52b  mov     [rsp+38h+var_10], ebx; <args_0>
0x18019f52f  xor     r9d, r9d; level
0x18019f532  mov     [rsp+38h+format], rax; format
0x18019f537  mov     r8d, 388h; line
0x18019f53d  lea     phProcessToken, aProcesstokenGe_0; "ProcessToken::GetProcessToken"
0x18019f544  lea     rcx, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x18019f54b  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18019f550  test    ebx, ebx
0x18019f552  jle     short loc_18019F55F
0x18019f554  movzx   ebx, bx
0x18019f557  or      ebx, 80070000h
0x18019f55d  test    ebx, ebx
0x18019f55f  js      short loc_18019F5D0
0x18019f561  mov     phProcessToken, [rsp+38h+hImpersonationToken]; Token
0x18019f566  xor     ecx, ecx; Thread
0x18019f568  call    cs:__imp_SetThreadToken
0x18019f56e  test    eax, eax
0x18019f570  jnz     short loc_18019F5D0
0x18019f572  call    cs:__imp_GetLastError
0x18019f578  mov     ebx, eax
0x18019f57a  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18019f580  test    eax, eax
0x18019f582  jnz     short loc_18019F597
0x18019f584  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18019f58a  jz      short loc_18019F5C3
0x18019f58c  xor     ecx, ecx; level
0x18019f58e  call    IsWppLevelEnabled
0x18019f593  test    al, al
0x18019f595  jz      short loc_18019F5C3
0x18019f597  lea     rax, aSetthreadtoken; "SetThreadToken failed: %!WINERROR!"
0x18019f59e  mov     [rsp+38h+var_10], ebx; <args_0>
0x18019f5a2  xor     r9d, r9d; level
0x18019f5a5  mov     [rsp+38h+format], rax; format
0x18019f5aa  mov     r8d, 391h; line
0x18019f5b0  lea     phProcessToken, aProcesstokenGe_0; "ProcessToken::GetProcessToken"
0x18019f5b7  lea     rcx, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x18019f5be  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18019f5c3  test    ebx, ebx
0x18019f5c5  jle     short loc_18019F5D0
0x18019f5c7  movzx   ebx, bx
0x18019f5ca  or      ebx, 80070000h
0x18019f5d0  mov     rcx, [rsp+38h+hImpersonationToken]; hObject
0x18019f5d5  call    cs:__imp_CloseHandle
0x18019f5db  test    ebx, ebx
0x18019f5dd  js      short loc_18019F5E7
0x18019f5df  mov     rcx, [rsp+38h+hProcessToken]
0x18019f5e4  mov     [rsi], rcx
0x18019f5e7  mov     rsi, [rsp+38h+arg_18]
0x18019f5ec  mov     eax, ebx
0x18019f5ee  mov     rbx, [rsp+38h+arg_10]
0x18019f5f3  add     rsp, 30h
0x18019f5f7  pop     rdi
0x18019f5f8  retn
```

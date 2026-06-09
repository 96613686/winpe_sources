# IsCurrentProcessFullTrust(bool *)

- ea: `0x18011f734`
- end: `0x18011f9a9`
- name: `?IsCurrentProcessFullTrust@@YAJPEA_N@Z`
- size: `629`
- prototype: `HRESULT __fastcall(bool *pCurrentProcessIsFullTrust)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016970`

## callees

- `0x18008db2c`
- `0x18011f734`
- `0x1801402f0`
- `0x1801457c0`
- `0x18014d5f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f8f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f8f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f991`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f991`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011f768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011f8db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011f768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011f8db`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18011f8d5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18011f95d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18011f8d5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18011f95d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011f779`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011f8ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011f779`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011f8ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011f7f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011f7f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011f80c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011f80c`

## string_xrefs

- `0x18011f7d1`: `onecore\com\combase\winrtbase\brokeredactivation.cpp`
- `0x18011f862`: `onecore\com\combase\winrtbase\brokeredactivation.cpp`
- `0x18011f8af`: `onecore\com\combase\winrtbase\brokeredactivation.cpp`
- `0x18011f93d`: `onecore\com\combase\winrtbase\brokeredactivation.cpp`
- `0x18011f846`: `Process does not have access to its own token`
- `0x18011f88f`: `OpenThreadToken failed: %!WINERROR!`
- `0x18011f7b1`: `OpenProcessToken failed: %!WINERROR!`
- `0x18011f91d`: `OpenProcessToken failed: %!WINERROR!`

## pseudocode

```c
__int64 __fastcall IsCurrentProcessFullTrust(bool *pCurrentProcessIsFullTrust)
{
  signed int v3; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // edi
  HANDLE CurrentThread; // rax
  bool v7; // sf
  HANDLE v8; // rax
  bool v9; // al
  void *hProcessToken; // [rsp+48h] [rbp+10h] BYREF
  void *hThreadToken; // [rsp+50h] [rbp+18h] BYREF

  if ( s_processTrust )
  {
    *pCurrentProcessIsFullTrust = s_processTrust == ProcessIsFullTrust;
    return 0;
  }
  v3 = 0;
  hProcessToken = 0;
  *pCurrentProcessIsFullTrust = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &hProcessToken) )
    goto LABEL_36;
  LastError = GetLastError();
  if ( LastError != 5 )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<unsigned int>(
        "onecore\\com\\combase\\winrtbase\\brokeredactivation.cpp",
        "IsCurrentProcessFullTrust",
        183,
        ERRORS,
        L"OpenProcessToken failed: %!WINERROR!",
        LastError);
    if ( LastError <= 0 )
    {
      v3 = LastError;
LABEL_34:
      v7 = v3 < 0;
      goto LABEL_35;
    }
    v3 = (unsigned __int16)LastError;
LABEL_25:
    v3 |= 0x80070000;
    goto LABEL_34;
  }
  hThreadToken = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &hThreadToken) )
  {
    SetThreadToken(0, 0);
    v8 = GetCurrentProcess();
    if ( !OpenProcessToken(v8, 8u, &hProcessToken) )
    {
      v3 = GetLastError();
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<unsigned int>(
          "onecore\\com\\combase\\winrtbase\\brokeredactivation.cpp",
          "IsCurrentProcessFullTrust",
          212,
          ERRORS,
          L"OpenProcessToken failed: %!WINERROR!",
          v3);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
    }
    SetThreadToken(0, hThreadToken);
    CloseHandle(hThreadToken);
    goto LABEL_34;
  }
  v3 = GetLastError();
  if ( v3 == 1008 )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<>(
        "onecore\\com\\combase\\winrtbase\\brokeredactivation.cpp",
        "IsCurrentProcessFullTrust",
        196,
        ERRORS,
        L"Process does not have access to its own token");
    return (unsigned int)-2147024891;
  }
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    ComTraceMessageT<unsigned int>(
      "onecore\\com\\combase\\winrtbase\\brokeredactivation.cpp",
      "IsCurrentProcessFullTrust",
      201,
      ERRORS,
      L"OpenThreadToken failed: %!WINERROR!",
      v3);
  v7 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3;
    goto LABEL_25;
  }
LABEL_35:
  if ( !v7 )
  {
LABEL_36:
    v9 = IsTokenILMediumOrGreater(hProcessToken);
    *pCurrentProcessIsFullTrust = v9;
    s_processTrust = !v9 + 1;
    CloseHandle(hProcessToken);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18011f734  mov     [rsp+arg_0], rbx
0x18011f739  mov     [rsp+arg_18], rsi
0x18011f73e  push    rdi
0x18011f73f  sub     rsp, 30h
0x18011f743  mov     eax, cs:s_processTrust
0x18011f749  mov     rsi, pCurrentProcessIsFullTrust
0x18011f74c  test    eax, eax
0x18011f74e  jz      short loc_18011F75F
0x18011f750  cmp     eax, 1
0x18011f753  setz    al
0x18011f756  mov     [pCurrentProcessIsFullTrust], al
0x18011f758  xor     eax, eax
0x18011f75a  jmp     loc_18011F999
0x18011f75f  xor     ebx, ebx
0x18011f761  mov     [rsp+38h+hProcessToken], rbx
0x18011f766  mov     [pCurrentProcessIsFullTrust], bl
0x18011f768  call    cs:__imp_GetCurrentProcess
0x18011f76e  mov     pCurrentProcessIsFullTrust, rax; ProcessHandle
0x18011f771  lea     r8, [rsp+38h+hProcessToken]; TokenHandle
0x18011f776  lea     edx, [rbx+8]; DesiredAccess
0x18011f779  call    cs:__imp_OpenProcessToken
0x18011f77f  test    eax, eax
0x18011f781  jnz     loc_18011F972
0x18011f787  call    cs:__imp_GetLastError
0x18011f78d  mov     edi, eax
0x18011f78f  cmp     eax, 5
0x18011f792  jz      short loc_18011F7F0
0x18011f794  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011f79a  test    eax, eax
0x18011f79c  jnz     short loc_18011F7B1
0x18011f79e  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18011f7a4  jz      short loc_18011F7DD
0x18011f7a6  xor     ecx, ecx; level
0x18011f7a8  call    IsWppLevelEnabled
0x18011f7ad  test    al, al
0x18011f7af  jz      short loc_18011F7DD
0x18011f7b1  lea     rax, aOpenprocesstok; "OpenProcessToken failed: %!WINERROR!"
0x18011f7b8  mov     [rsp+38h+var_10], edi; <args_0>
0x18011f7bc  xor     r9d, r9d; level
0x18011f7bf  mov     [rsp+38h+format], rax; format
0x18011f7c4  mov     r8d, 0B7h; line
0x18011f7ca  lea     rdx, aIscurrentproce; "IsCurrentProcessFullTrust"
0x18011f7d1  lea     pCurrentProcessIsFullTrust, aOnecoreComComb_73; "onecore\\com\\combase\\winrtbase\\broke"...
0x18011f7d8  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18011f7dd  test    edi, edi
0x18011f7df  jg      short loc_18011F7E8
0x18011f7e1  mov     ebx, edi
0x18011f7e3  jmp     loc_18011F96E
0x18011f7e8  movzx   ebx, di
0x18011f7eb  jmp     loc_18011F8C6
0x18011f7f0  mov     [rsp+38h+hThreadToken], rbx
0x18011f7f5  call    cs:__imp_GetCurrentThread
0x18011f7fb  mov     edx, 4; DesiredAccess
0x18011f800  lea     r9, [rsp+38h+hThreadToken]; TokenHandle
0x18011f805  mov     pCurrentProcessIsFullTrust, rax; ThreadHandle
0x18011f808  lea     r8d, [rdx-3]; OpenAsSelf
0x18011f80c  call    cs:__imp_OpenThreadToken
0x18011f812  test    eax, eax
0x18011f814  jnz     loc_18011F8D1
0x18011f81a  call    cs:__imp_GetLastError
0x18011f820  mov     ebx, eax
0x18011f822  cmp     eax, 3F0h
0x18011f827  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011f82d  jnz     short loc_18011F878
0x18011f82f  test    eax, eax
0x18011f831  jnz     short loc_18011F846
0x18011f833  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18011f839  jz      short loc_18011F86E
0x18011f83b  xor     ecx, ecx; level
0x18011f83d  call    IsWppLevelEnabled
0x18011f842  test    al, al
0x18011f844  jz      short loc_18011F86E
0x18011f846  lea     rax, aProcessDoesNot_0; "Process does not have access to its own"...
0x18011f84d  xor     r9d, r9d; level
0x18011f850  mov     r8d, 0C4h; line
0x18011f856  mov     [rsp+38h+format], rax; format
0x18011f85b  lea     rdx, aIscurrentproce; "IsCurrentProcessFullTrust"
0x18011f862  lea     pCurrentProcessIsFullTrust, aOnecoreComComb_73; "onecore\\com\\combase\\winrtbase\\broke"...
0x18011f869  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18011f86e  mov     ebx, 80070005h
0x18011f873  jmp     loc_18011F997
0x18011f878  test    eax, eax
0x18011f87a  jnz     short loc_18011F88F
0x18011f87c  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18011f882  jz      short loc_18011F8BB
0x18011f884  xor     ecx, ecx; level
0x18011f886  call    IsWppLevelEnabled
0x18011f88b  test    al, al
0x18011f88d  jz      short loc_18011F8BB
0x18011f88f  lea     rax, aOpenthreadtoke_0; "OpenThreadToken failed: %!WINERROR!"
0x18011f896  mov     [rsp+38h+var_10], ebx; <args_0>
0x18011f89a  xor     r9d, r9d; level
0x18011f89d  mov     [rsp+38h+format], rax; format
0x18011f8a2  mov     r8d, 0C9h; line
0x18011f8a8  lea     rdx, aIscurrentproce; "IsCurrentProcessFullTrust"
0x18011f8af  lea     pCurrentProcessIsFullTrust, aOnecoreComComb_73; "onecore\\com\\combase\\winrtbase\\broke"...
0x18011f8b6  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18011f8bb  test    ebx, ebx
0x18011f8bd  jle     loc_18011F970
0x18011f8c3  movzx   ebx, bx
0x18011f8c6  or      ebx, 80070000h
0x18011f8cc  jmp     loc_18011F96E
0x18011f8d1  xor     edx, edx; Token
0x18011f8d3  xor     ecx, ecx; Thread
0x18011f8d5  call    cs:__imp_SetThreadToken
0x18011f8db  call    cs:__imp_GetCurrentProcess
0x18011f8e1  lea     r8, [rsp+38h+hProcessToken]; TokenHandle
0x18011f8e6  mov     edx, 8; DesiredAccess
0x18011f8eb  mov     pCurrentProcessIsFullTrust, rax; ProcessHandle
0x18011f8ee  call    cs:__imp_OpenProcessToken
0x18011f8f4  test    eax, eax
0x18011f8f6  jnz     short loc_18011F956
0x18011f8f8  call    cs:__imp_GetLastError
0x18011f8fe  mov     ebx, eax
0x18011f900  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011f906  test    eax, eax
0x18011f908  jnz     short loc_18011F91D
0x18011f90a  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18011f910  jz      short loc_18011F949
0x18011f912  xor     ecx, ecx; level
0x18011f914  call    IsWppLevelEnabled
0x18011f919  test    al, al
0x18011f91b  jz      short loc_18011F949
0x18011f91d  lea     rax, aOpenprocesstok; "OpenProcessToken failed: %!WINERROR!"
0x18011f924  mov     [rsp+38h+var_10], ebx; <args_0>
0x18011f928  xor     r9d, r9d; level
0x18011f92b  mov     [rsp+38h+format], rax; format
0x18011f930  mov     r8d, 0D4h; line
0x18011f936  lea     rdx, aIscurrentproce; "IsCurrentProcessFullTrust"
0x18011f93d  lea     pCurrentProcessIsFullTrust, aOnecoreComComb_73; "onecore\\com\\combase\\winrtbase\\broke"...
0x18011f944  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18011f949  test    ebx, ebx
0x18011f94b  jle     short loc_18011F956
0x18011f94d  movzx   ebx, bx
0x18011f950  or      ebx, 80070000h
0x18011f956  mov     rdx, [rsp+38h+hThreadToken]; Token
0x18011f95b  xor     ecx, ecx; Thread
0x18011f95d  call    cs:__imp_SetThreadToken
0x18011f963  mov     pCurrentProcessIsFullTrust, [rsp+38h+hThreadToken]; hObject
0x18011f968  call    cs:__imp_CloseHandle
0x18011f96e  test    ebx, ebx
0x18011f970  js      short loc_18011F997
0x18011f972  mov     pCurrentProcessIsFullTrust, [rsp+38h+hProcessToken]; hToken
0x18011f977  call    ?IsTokenILMediumOrGreater@@YA_NPEAX@Z; IsTokenILMediumOrGreater(void *)
0x18011f97c  movzx   ecx, al
0x18011f97f  mov     [rsi], cl
0x18011f981  xor     ecx, 1
0x18011f984  inc     ecx
0x18011f986  mov     cs:s_processTrust, ecx
0x18011f98c  mov     pCurrentProcessIsFullTrust, [rsp+38h+hProcessToken]; hObject
0x18011f991  call    cs:__imp_CloseHandle
0x18011f997  mov     eax, ebx
0x18011f999  mov     rbx, [rsp+38h+arg_0]
0x18011f99e  mov     rsi, [rsp+38h+arg_18]
0x18011f9a3  add     rsp, 30h
0x18011f9a7  pop     rdi
0x18011f9a8  retn
```

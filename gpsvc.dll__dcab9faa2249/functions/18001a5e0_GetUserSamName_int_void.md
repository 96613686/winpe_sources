# GetUserSamName(int,void *)

- ea: `0x18001a5e0`
- end: `0x18001a93f`
- name: `?GetUserSamName@@YAPEAGHPEAX@Z`
- size: `863`
- prototype: `unsigned __int16 *(int, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180022d38`
- `0x1800a74c0`

## callees

- `0x18001a5e0`
- `0x18001ae40`
- `0x18001ae60`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a90c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a90c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a76d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a76d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a631`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a631`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a618`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a618`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a79b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a79b`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001a89f`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001a89f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a8f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a8f3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a694`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a694`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a8d3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a8d3`
- `SspiCli!GetUserNameExW` at `0x18001a866`
- `SspiCli!GetUserNameExW` at `0x18001a866`

## string_xrefs

- `0x18001a665`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x18001a688`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x18001a6d0`: `ImpersonateUser: Failed to impersonate user with %d.`
- `0x18001a701`: `ImpersonateUser: Failed to impersonate user with %d.`
- `0x18001a73a`: `Failed to impersonate the user with 0x%x`
- `0x18001a776`: `Failed to impersonate the user with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall GetUserSamName(int a1, void *a2)
{
  int v3; // r14d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void (*v6)(unsigned int, const unsigned __int16 *, ...); // rbx
  const wchar_t *v7; // rdx
  DWORD v8; // eax
  WCHAR *v9; // rdi
  void (*v10)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD v13; // ebx
  int v14; // esi
  WCHAR *v15; // rax
  ULONG nSize; // [rsp+20h] [rbp-79h] BYREF
  void *TokenHandle[2]; // [rsp+28h] [rbp-71h] BYREF
  void *v19[5]; // [rsp+38h] [rbp-61h] BYREF
  int v20; // [rsp+64h] [rbp-35h]
  int v21; // [rsp+68h] [rbp-31h]
  int v22; // [rsp+88h] [rbp-11h]
  __int64 v23; // [rsp+A8h] [rbp+Fh]

  TokenHandle[0] = 0;
  v3 = 0;
  if ( !a1 )
  {
    CurrentThread = GetCurrentThread();
    v3 = 1;
    if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, TokenHandle) )
    {
      TokenHandle[0] = 0;
      LastError = GetLastError();
      if ( LastError != 1008 )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_20;
        v6 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(4u, L"ImpersonateUser: Failed to open thread token with %d.", LastError);
          goto LABEL_20;
        }
        v7 = L"ImpersonateUser: Failed to open thread token with %d.";
LABEL_16:
        v6(4u, v7, LastError);
LABEL_20:
        v9 = 0;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v10 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v11 = GetLastError();
            v10(2u, L"Failed to impersonate the user with 0x%x", v11);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v12 = GetLastError();
            RedirectDebugMsg(2u, L"Failed to impersonate the user with 0x%x", v12);
          }
        }
        return v9;
      }
    }
    if ( !ImpersonateLoggedOnUser(a2) )
    {
      if ( TokenHandle[0] )
      {
        CloseHandle(TokenHandle[0]);
        TokenHandle[0] = 0;
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_20;
      v6 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v8 = GetLastError();
          RedirectDebugMsg(4u, L"ImpersonateUser: Failed to impersonate user with %d.", v8);
        }
        goto LABEL_20;
      }
      LastError = GetLastError();
      v7 = L"ImpersonateUser: Failed to impersonate user with %d.";
      goto LABEL_16;
    }
  }
  nSize = 75;
  v9 = (WCHAR *)LocalAlloc(0x40u, 0x96u);
  if ( v9 )
  {
    v14 = 0;
    while ( 1 )
    {
      v19[0] = 0;
      v19[1] = 0;
      v19[2] = API_CALL_TRACING_END_SUCCESS;
      v19[3] = 0;
      v19[4] = "i\x1B";
      TokenHandle[1] = &CAPICallScenarioEvent::`vftable';
      v20 = 0;
      v21 = 4117;
      v22 = 4118;
      v23 = 0;
      if ( GetUserNameExW(NameSamCompatible, v9, &nSize) )
        break;
      v13 = GetLastError();
      if ( nSize && (v13 == 122 || v13 == 234) )
      {
        v15 = (WCHAR *)LocalReAlloc(v9, 2LL * nSize, 2u);
        if ( !v15 )
        {
          v13 = GetLastError();
LABEL_47:
          LocalFree(v9);
          v9 = 0;
          goto LABEL_49;
        }
        v9 = v15;
      }
      else
      {
        switch ( v13 )
        {
          case 0x534u:
            goto LABEL_47;
          case 0x4CFu:
            goto LABEL_47;
          case 0x54Bu:
            goto LABEL_47;
        }
        if ( (unsigned int)++v14 > 3 )
          goto LABEL_47;
        Sleep(0x1F4u);
      }
      CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(v19);
    }
    v13 = 0;
LABEL_49:
    CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(v19);
  }
  else
  {
    v13 = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"MyGetUserName:  Failed to allocate memory with %d", v13);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"MyGetUserName:  Failed to allocate memory with %d", v13);
      }
    }
  }
  SetLastError(v13);
  if ( v3 )
    RevertToUser(TokenHandle);
  return v9;
}

```

## disassembly

```asm
0x18001a5e0  push    rbp
0x18001a5e2  push    rbx
0x18001a5e3  push    rsi
0x18001a5e4  push    rdi
0x18001a5e5  push    r14
0x18001a5e7  push    r15
0x18001a5e9  lea     rbp, [rsp-2Fh]
0x18001a5ee  sub     rsp, 0C8h
0x18001a5f5  mov     rax, cs:__security_cookie
0x18001a5fc  xor     rax, rsp
0x18001a5ff  mov     [rbp+57h+var_40], rax
0x18001a603  mov     rbx, rdx
0x18001a606  xor     r15d, r15d
0x18001a609  mov     [rbp+57h+TokenHandle], r15
0x18001a60d  mov     r14d, r15d
0x18001a610  test    ecx, ecx
0x18001a612  jnz     loc_18001A78C
0x18001a618  call    cs:__imp_GetCurrentThread
0x18001a61e  mov     rcx, rax; ThreadHandle
0x18001a621  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001a625  lea     r14d, [r15+1]
0x18001a629  mov     r8d, r14d; OpenAsSelf
0x18001a62c  mov     edx, 2000Ch; DesiredAccess
0x18001a631  call    cs:__imp_OpenThreadToken
0x18001a637  test    eax, eax
0x18001a639  jnz     short loc_18001A691
0x18001a63b  mov     [rbp+57h+TokenHandle], r15
0x18001a63f  call    cs:__imp_GetLastError
0x18001a645  cmp     eax, 3F0h
0x18001a64a  jz      short loc_18001A691
0x18001a64c  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18001a653  jz      loc_18001A715
0x18001a659  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001a660  test    rbx, rbx
0x18001a663  jz      short loc_18001A66E
0x18001a665  lea     rdx, aImpersonateuse; "ImpersonateUser: Failed to open thread "...
0x18001a66c  jmp     short loc_18001A6D7
0x18001a66e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18001a675  jz      loc_18001A715
0x18001a67b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001a682  jz      loc_18001A715
0x18001a688  lea     rdx, aImpersonateuse; "ImpersonateUser: Failed to open thread "...
0x18001a68f  jmp     short loc_18001A708
0x18001a691  mov     rcx, rbx; hToken
0x18001a694  call    cs:__imp_ImpersonateLoggedOnUser
0x18001a69a  test    eax, eax
0x18001a69c  jnz     loc_18001A78C
0x18001a6a2  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001a6a6  test    rcx, rcx
0x18001a6a9  jz      short loc_18001A6B5
0x18001a6ab  call    cs:__imp_CloseHandle
0x18001a6b1  mov     [rbp+57h+TokenHandle], r15
0x18001a6b5  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18001a6bc  jz      short loc_18001A715
0x18001a6be  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001a6c5  test    rbx, rbx
0x18001a6c8  jz      short loc_18001A6E9
0x18001a6ca  call    cs:__imp_GetLastError
0x18001a6d0  lea     rdx, aImpersonateuse_0; "ImpersonateUser: Failed to impersonate "...
0x18001a6d7  mov     r8d, eax
0x18001a6da  mov     ecx, 4
0x18001a6df  mov     rax, rbx
0x18001a6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6e7  jmp     short loc_18001A715
0x18001a6e9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18001a6f0  jz      short loc_18001A715
0x18001a6f2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001a6f9  jz      short loc_18001A715
0x18001a6fb  call    cs:__imp_GetLastError
0x18001a701  lea     rdx, aImpersonateuse_0; "ImpersonateUser: Failed to impersonate "...
0x18001a708  mov     r8d, eax
0x18001a70b  mov     ecx, 4; unsigned int
0x18001a710  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001a715  mov     rdi, r15
0x18001a718  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18001a71f  jz      loc_18001A920
0x18001a725  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001a72c  test    rbx, rbx
0x18001a72f  jz      short loc_18001A753
0x18001a731  call    cs:__imp_GetLastError
0x18001a737  mov     r8d, eax
0x18001a73a  lea     rdx, aFailedToImpers_1; "Failed to impersonate the user with 0x%"...
0x18001a741  mov     ecx, 2
0x18001a746  mov     rax, rbx
0x18001a749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a74e  jmp     loc_18001A920
0x18001a753  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18001a75a  jz      loc_18001A920
0x18001a760  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001a767  jz      loc_18001A920
0x18001a76d  call    cs:__imp_GetLastError
0x18001a773  mov     r8d, eax
0x18001a776  lea     rdx, aFailedToImpers_1; "Failed to impersonate the user with 0x%"...
0x18001a77d  mov     ecx, 2; unsigned int
0x18001a782  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001a787  jmp     loc_18001A920
0x18001a78c  mov     [rbp+57h+nSize], 4Bh ; 'K'
0x18001a793  mov     edx, 96h; uBytes
0x18001a798  lea     ecx, [rdx-56h]; uFlags
0x18001a79b  call    cs:__imp_LocalAlloc
0x18001a7a1  mov     rdi, rax
0x18001a7a4  test    rax, rax
0x18001a7a7  jnz     short loc_18001A814
0x18001a7a9  call    cs:__imp_GetLastError
0x18001a7af  mov     ebx, eax
0x18001a7b1  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18001a7b8  jz      loc_18001A90A
0x18001a7be  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001a7c5  test    rax, rax
0x18001a7c8  jz      short loc_18001A7E1
0x18001a7ca  mov     r8d, ebx
0x18001a7cd  lea     rdx, aMygetusernameF; "MyGetUserName:  Failed to allocate memo"...
0x18001a7d4  lea     ecx, [rdi+2]
0x18001a7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7dc  jmp     loc_18001A90A
0x18001a7e1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18001a7e8  jz      loc_18001A90A
0x18001a7ee  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001a7f5  jz      loc_18001A90A
0x18001a7fb  mov     r8d, ebx
0x18001a7fe  lea     rdx, aMygetusernameF; "MyGetUserName:  Failed to allocate memo"...
0x18001a805  mov     ecx, 2; unsigned int
0x18001a80a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001a80f  jmp     loc_18001A90A
0x18001a814  mov     esi, r15d
0x18001a817  mov     [rbp+57h+var_B8], r15
0x18001a81b  mov     [rbp+57h+var_B0], r15
0x18001a81f  lea     rax, API_CALL_TRACING_END_SUCCESS
0x18001a826  mov     [rbp+57h+var_A8], rax
0x18001a82a  mov     [rbp+57h+var_A0], r15
0x18001a82e  lea     rax, API_CALL_TRACING_END_FAILURE; "i\x1B"
0x18001a835  mov     [rbp+57h+var_98], rax
0x18001a839  lea     rax, ??_7CAPICallScenarioEvent@@6B@; const CAPICallScenarioEvent::`vftable'
0x18001a840  mov     [rbp+57h+var_C0], rax
0x18001a844  mov     [rbp+57h+var_8C], r15d
0x18001a848  mov     [rbp+57h+var_88], 1015h
0x18001a84f  mov     [rbp+57h+var_68], 1016h
0x18001a856  mov     [rbp+57h+var_48], r15
0x18001a85a  lea     r8, [rbp+57h+nSize]; nSize
0x18001a85e  mov     rdx, rdi; lpNameBuffer
0x18001a861  mov     ecx, 2; NameFormat
0x18001a866  call    cs:__imp_GetUserNameExW
0x18001a86c  test    al, al
0x18001a86e  jnz     loc_18001A8FE
0x18001a874  call    cs:__imp_GetLastError
0x18001a87a  mov     ebx, eax
0x18001a87c  mov     eax, [rbp+57h+nSize]
0x18001a87f  test    eax, eax
0x18001a881  jz      short loc_18001A8AF
0x18001a883  cmp     ebx, 7Ah ; 'z'
0x18001a886  jz      short loc_18001A890
0x18001a888  cmp     ebx, 0EAh
0x18001a88e  jnz     short loc_18001A8AF
0x18001a890  mov     rdx, rax
0x18001a893  add     rdx, rdx; uBytes
0x18001a896  mov     r8d, 2; uFlags
0x18001a89c  mov     rcx, rdi; hMem
0x18001a89f  call    cs:__imp_LocalReAlloc
0x18001a8a5  test    rax, rax
0x18001a8a8  jz      short loc_18001A8E8
0x18001a8aa  mov     rdi, rax
0x18001a8ad  jmp     short loc_18001A8DA
0x18001a8af  cmp     ebx, 534h
0x18001a8b5  jz      short loc_18001A8F0
0x18001a8b7  cmp     ebx, 4CFh
0x18001a8bd  jz      short loc_18001A8F0
0x18001a8bf  cmp     ebx, 54Bh
0x18001a8c5  jz      short loc_18001A8F0
0x18001a8c7  inc     esi
0x18001a8c9  cmp     esi, 3
0x18001a8cc  ja      short loc_18001A8F0
0x18001a8ce  mov     ecx, 1F4h; dwMilliseconds
0x18001a8d3  call    cs:__imp_Sleep
0x18001a8d9  nop
0x18001a8da  lea     rcx, [rbp+57h+var_B8]; this
0x18001a8de  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x18001a8e3  jmp     loc_18001A817
0x18001a8e8  call    cs:__imp_GetLastError
0x18001a8ee  mov     ebx, eax
0x18001a8f0  mov     rcx, rdi; hMem
0x18001a8f3  call    cs:__imp_LocalFree
0x18001a8f9  mov     rdi, r15
0x18001a8fc  jmp     short loc_18001A901
0x18001a8fe  mov     ebx, r15d
0x18001a901  lea     rcx, [rbp+57h+var_B8]; this
0x18001a905  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x18001a90a  mov     ecx, ebx; dwErrCode
0x18001a90c  call    cs:__imp_SetLastError
0x18001a912  test    r14d, r14d
0x18001a915  jz      short loc_18001A920
0x18001a917  lea     rcx, [rbp+57h+TokenHandle]; void **
0x18001a91b  call    ?RevertToUser@@YAHPEAPEAX@Z; RevertToUser(void * *)
0x18001a920  mov     rax, rdi
0x18001a923  mov     rcx, [rbp+57h+var_40]
0x18001a927  xor     rcx, rsp; StackCookie
0x18001a92a  call    __security_check_cookie
0x18001a92f  add     rsp, 0C8h
0x18001a936  pop     r15
0x18001a938  pop     r14
0x18001a93a  pop     rdi
0x18001a93b  pop     rsi
0x18001a93c  pop     rbx
0x18001a93d  pop     rbp
0x18001a93e  retn
```

# LaunchUserProcessInSession(ushort const *,ulong,void *)

- ea: `0x18009362c`
- end: `0x180093b44`
- name: `?LaunchUserProcessInSession@@YAKPEBGKPEAX@Z`
- size: `1304`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180093e90`

## callees

- `0x18000a504`
- `0x18000a52c`
- `0x18001ee6c`
- `0x18002c690`
- `0x180039148`
- `0x180052fe0`
- `0x1800565d0`
- `0x180075ec0`
- `0x18007de08`
- `0x18009362c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800937ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800937ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093a3e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180093a34`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180093a34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093724`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093724`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180093856`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180093856`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800937c4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800937c4`
- `profapi!__imp_CreateEnvBlock` at `0x1800938e7`
- `profapi!__imp_CreateEnvBlock` at `0x1800938e7`
- `profapi!__imp_DestroyEnvBlock` at `0x180093b02`
- `profapi!__imp_DestroyEnvBlock` at `0x180093b02`

## string_xrefs

- `0x1800936a0`: `gpscript.exe /RefreshSystemParam`
- `0x1800936cd`: `gpscript.exe /RefreshSystemParam`
- `0x180093791`: `gpscript.exe /RefreshSystemParam`
- `0x1800936a7`: `Launching user process : CommandLine is <%ws> in session %d`
- `0x1800936d4`: `Launching user process : CommandLine is <%ws> in session %d`
- `0x180093755`: `Command Line LocalAlloc failed`
- `0x180093778`: `Command Line LocalAlloc failed`
- `0x1800937ee`: `Failed to duplicate token = 0x%x`
- `0x18009381f`: `Failed to duplicate token = 0x%x`
- `0x180093880`: `Failed to set token information = 0x%x`
- `0x1800938a6`: `Failed to set token information = 0x%x`
- `0x18009391f`: `Failed to revert back user impersonation = 0x%x`
- `0x180093942`: `Failed to revert back user impersonation = 0x%x`
- `0x1800939be`: `Failed to revert back user impersonation = 0x%x`
- `0x1800939e7`: `Failed to revert back user impersonation = 0x%x`
- `0x18009396c`: `Failed to create environment block = 0x%x`
- `0x180093992`: `Failed to create environment block = 0x%x`
- `0x180093ac0`: `Failed to impersonate user with error = 0x%x`
- `0x180093ae6`: `Failed to impersonate user with error = 0x%x`
- `0x180093a5e`: `Failed in CreateProcessAsUser = 0x%x`
- `0x180093a80`: `Failed in CreateProcessAsUser = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall LaunchUserProcessInSession(unsigned __int16 *a1, unsigned int a2, void *a3)
{
  HLOCAL v5; // rax
  WCHAR *v6; // rbx
  DWORD LastError; // edi
  void (*v8)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v9; // rdx
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  LPWSTR lpCommandLine; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v18[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-70h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE TokenHandle; // [rsp+150h] [rbp+50h] BYREF
  unsigned int TokenInformation; // [rsp+158h] [rbp+58h] BYREF
  LPVOID lpEnvironment; // [rsp+168h] [rbp+68h] BYREF

  TokenInformation = a2;
  TokenHandle = a1;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  TokenHandle = 0;
  lpCommandLine = 0;
  v17 = 0;
  lpEnvironment = 0;
  v16 = 0;
  v15 = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(
        4u,
        L"Launching user process : CommandLine is <%ws> in session %d",
        L"gpscript.exe /RefreshSystemParam",
        a2);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(
        4u,
        L"Launching user process : CommandLine is <%ws> in session %d",
        L"gpscript.exe /RefreshSystemParam",
        a2);
    }
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.wShowWindow = 2;
  StartupInfo.lpDesktop = L"Winsta0\\Default";
  StartupInfo.dwFlags = 0;
  v5 = LocalAlloc(0x40u, 0x42u);
  XPtrLF<unsigned short>::operator=(&lpCommandLine, v5);
  v6 = lpCommandLine;
  if ( !lpCommandLine )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Command Line LocalAlloc failed");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Command Line LocalAlloc failed");
      }
    }
    LastError = 14;
    goto LABEL_66;
  }
  StringCchCopyW(lpCommandLine, 0x21u, L"gpscript.exe /RefreshSystemParam");
  if ( DuplicateTokenEx(a3, 0x1ABu, 0, SecurityImpersonation, TokenPrimary, &TokenHandle) )
  {
    XHandle::operator=(&v17, TokenHandle);
    if ( SetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u) )
    {
      v18[0] = &CToken::`vftable';
      v18[1] = TokenHandle;
      LastError = CToken::Impersonate((CToken *)v18, &TokenHandle);
      if ( LastError )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_66;
        v8 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v9 = L"Failed to impersonate user with error = 0x%x";
          goto LABEL_62;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"Failed to impersonate user with error = 0x%x", LastError);
      }
      else
      {
        v10 = CreateEnvBlock(&lpEnvironment, TokenHandle, 0);
        LOWORD(LastError) = v10;
        if ( v10 >= 0 )
        {
          v12 = CToken::Revert((CToken *)v18, &TokenHandle);
          if ( v12 && *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"Failed to revert back user impersonation = 0x%x", v12);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"Failed to revert back user impersonation = 0x%x", v12);
            }
          }
          if ( CreateProcessAsUserW(
                 TokenHandle,
                 0,
                 v6,
                 0,
                 0,
                 0,
                 0x400u,
                 lpEnvironment,
                 0,
                 &StartupInfo,
                 &ProcessInformation) )
          {
            XHandle::operator=(&v16, ProcessInformation.hThread);
            XHandle::operator=(&v15, ProcessInformation.hProcess);
            LastError = 0;
            goto LABEL_66;
          }
          LastError = GetLastError();
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_66;
          v8 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v9 = L"Failed in CreateProcessAsUser = 0x%x";
            goto LABEL_62;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"Failed in CreateProcessAsUser = 0x%x", LastError);
        }
        else
        {
          v11 = CToken::Revert((CToken *)v18, &TokenHandle);
          if ( v11 && *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"Failed to revert back user impersonation = 0x%x", v11);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"Failed to revert back user impersonation = 0x%x", v11);
            }
          }
          LastError = (unsigned __int16)LastError;
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v8 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v9 = L"Failed to create environment block = 0x%x";
              goto LABEL_62;
            }
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(2u, L"Failed to create environment block = 0x%x", (unsigned __int16)LastError);
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_66;
      v8 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v9 = L"Failed to set token information = 0x%x";
        goto LABEL_62;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"Failed to set token information = 0x%x", LastError);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_66;
    v8 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v9 = L"Failed to duplicate token = 0x%x";
LABEL_62:
      v8(2u, v9, LastError);
      goto LABEL_66;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      RedirectDebugMsg(2u, L"Failed to duplicate token = 0x%x", LastError);
  }
LABEL_66:
  if ( lpEnvironment )
    DestroyEnvBlock();
  XHandle::~XHandle((XHandle *)&v15);
  XHandle::~XHandle((XHandle *)&v16);
  XHandle::~XHandle((XHandle *)&v17);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&lpCommandLine);
  return LastError;
}

```

## disassembly

```asm
0x18009362c  mov     [rsp-8+TokenInformation], edx
0x180093630  mov     [rsp-8+TokenHandle], rcx
0x180093635  push    rbp
0x180093636  push    rbx
0x180093637  push    rsi
0x180093638  push    rdi
0x180093639  push    r14
0x18009363b  lea     rbp, [rsp-20h]
0x180093640  sub     rsp, 120h
0x180093647  mov     rdi, r8
0x18009364a  mov     ebx, edx
0x18009364c  xorps   xmm0, xmm0
0x18009364f  xor     eax, eax
0x180093651  movups  xmmword ptr [rbp+40h+ProcessInformation.hProcess], xmm0
0x180093655  mov     qword ptr [rbp+40h+ProcessInformation.dwProcessId], rax
0x180093659  lea     r14d, [rax+68h]
0x18009365d  mov     r8d, r14d; Size
0x180093660  xor     edx, edx; Val
0x180093662  lea     rcx, [rbp+40h+StartupInfo]; void *
0x180093666  call    memset_0
0x18009366b  xor     esi, esi
0x18009366d  mov     [rbp+40h+TokenHandle], rsi
0x180093671  mov     [rsp+140h+lpCommandLine], rsi
0x180093676  mov     [rsp+140h+var_C8], rsi
0x18009367b  mov     [rbp+40h+arg_18], rsi
0x18009367f  mov     [rsp+140h+var_D0], rsi
0x180093684  mov     [rsp+140h+var_D8], rsi
0x180093689  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18009368f  jz      short loc_1800936E5
0x180093691  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093698  test    rax, rax
0x18009369b  jz      short loc_1800936B8
0x18009369d  mov     r9d, ebx
0x1800936a0  lea     r8, aGpscriptExeRef; "gpscript.exe /RefreshSystemParam"
0x1800936a7  lea     rdx, aLaunchingUserP; "Launching user process : CommandLine is"...
0x1800936ae  lea     ecx, [rsi+4]
0x1800936b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800936b6  jmp     short loc_1800936E5
0x1800936b8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800936bf  jz      short loc_1800936E5
0x1800936c1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800936c8  jz      short loc_1800936E5
0x1800936ca  mov     r9d, ebx
0x1800936cd  lea     r8, aGpscriptExeRef; "gpscript.exe /RefreshSystemParam"
0x1800936d4  lea     rdx, aLaunchingUserP; "Launching user process : CommandLine is"...
0x1800936db  mov     ecx, 4; unsigned int
0x1800936e0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800936e5  xorps   xmm0, xmm0
0x1800936e8  xor     eax, eax
0x1800936ea  movups  xmmword ptr [rbp+40h+ProcessInformation.hProcess], xmm0
0x1800936ee  mov     qword ptr [rbp+40h+ProcessInformation.dwProcessId], rax
0x1800936f2  mov     r8, r14; Size
0x1800936f5  xor     edx, edx; Val
0x1800936f7  lea     rcx, [rbp+40h+StartupInfo]; void *
0x1800936fb  call    memset_0
0x180093700  mov     [rbp+40h+StartupInfo.cb], r14d
0x180093704  mov     r14d, 2
0x18009370a  mov     [rbp+40h+StartupInfo.wShowWindow], r14w
0x18009370f  lea     rax, aWinsta0Default; "Winsta0\\Default"
0x180093716  mov     [rbp+40h+StartupInfo.lpDesktop], rax
0x18009371a  mov     [rbp+40h+StartupInfo.dwFlags], esi
0x18009371d  lea     edx, [r14+40h]; uBytes
0x180093721  lea     ecx, [rdx-2]; uFlags
0x180093724  call    cs:__imp_LocalAlloc
0x18009372a  mov     rdx, rax
0x18009372d  lea     rcx, [rsp+140h+lpCommandLine]
0x180093732  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x180093737  mov     rbx, [rsp+140h+lpCommandLine]
0x18009373c  test    rbx, rbx
0x18009373f  jnz     short loc_180093791
0x180093741  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180093747  jz      short loc_180093787
0x180093749  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093750  test    rax, rax
0x180093753  jz      short loc_180093766
0x180093755  lea     rdx, aCommandLineLoc; "Command Line LocalAlloc failed"
0x18009375c  mov     ecx, r14d
0x18009375f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093764  jmp     short loc_180093787
0x180093766  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18009376d  jz      short loc_180093787
0x18009376f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093776  jz      short loc_180093787
0x180093778  lea     rdx, aCommandLineLoc; "Command Line LocalAlloc failed"
0x18009377f  mov     ecx, r14d; unsigned int
0x180093782  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093787  mov     edi, 0Eh
0x18009378c  jmp     loc_180093AF9
0x180093791  lea     r8, aGpscriptExeRef; "gpscript.exe /RefreshSystemParam"
0x180093798  mov     edx, 21h ; '!'; unsigned __int64
0x18009379d  mov     rcx, rbx; unsigned __int16 *
0x1800937a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800937a5  lea     rax, [rbp+40h+TokenHandle]
0x1800937a9  mov     [rsp+140h+phNewToken], rax; phNewToken
0x1800937ae  mov     [rsp+140h+TokenType], 1; TokenType
0x1800937b6  mov     r9d, r14d; ImpersonationLevel
0x1800937b9  xor     r8d, r8d; lpTokenAttributes
0x1800937bc  mov     edx, 1ABh; dwDesiredAccess
0x1800937c1  mov     rcx, rdi; hExistingToken
0x1800937c4  call    cs:__imp_DuplicateTokenEx
0x1800937ca  test    eax, eax
0x1800937cc  jnz     short loc_180093836
0x1800937ce  call    cs:__imp_GetLastError
0x1800937d4  mov     edi, eax
0x1800937d6  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800937dc  jz      loc_180093AF9
0x1800937e2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800937e9  test    rax, rax
0x1800937ec  jz      short loc_180093805
0x1800937ee  lea     rdx, aFailedToDuplic; "Failed to duplicate token = 0x%x"
0x1800937f5  mov     r8d, edi
0x1800937f8  mov     ecx, r14d
0x1800937fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093800  jmp     loc_180093AF9
0x180093805  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18009380c  jz      loc_180093AF9
0x180093812  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093819  jz      loc_180093AF9
0x18009381f  lea     rdx, aFailedToDuplic; "Failed to duplicate token = 0x%x"
0x180093826  mov     r8d, edi
0x180093829  mov     ecx, r14d; unsigned int
0x18009382c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093831  jmp     loc_180093AF9
0x180093836  mov     rdx, [rbp+40h+TokenHandle]
0x18009383a  lea     rcx, [rsp+140h+var_C8]
0x18009383f  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x180093844  mov     r9d, 4; TokenInformationLength
0x18009384a  lea     r8, [rbp+40h+TokenInformation]; TokenInformation
0x18009384e  lea     edx, [r9+8]; TokenInformationClass
0x180093852  mov     rcx, [rbp+40h+TokenHandle]; TokenHandle
0x180093856  call    cs:__imp_SetTokenInformation
0x18009385c  test    eax, eax
0x18009385e  jnz     short loc_1800938B2
0x180093860  call    cs:__imp_GetLastError
0x180093866  mov     edi, eax
0x180093868  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18009386e  jz      loc_180093AF9
0x180093874  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009387b  test    rax, rax
0x18009387e  jz      short loc_18009388C
0x180093880  lea     rdx, aFailedToSetTok; "Failed to set token information = 0x%x"
0x180093887  jmp     loc_1800937F5
0x18009388c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180093893  jz      loc_180093AF9
0x180093899  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800938a0  jz      loc_180093AF9
0x1800938a6  lea     rdx, aFailedToSetTok; "Failed to set token information = 0x%x"
0x1800938ad  jmp     loc_180093826
0x1800938b2  lea     rax, ??_7CToken@@6B@; const CToken::`vftable'
0x1800938b9  mov     [rbp+40h+var_C0], rax
0x1800938bd  mov     rax, [rbp+40h+TokenHandle]
0x1800938c1  mov     [rbp+40h+var_B8], rax
0x1800938c5  lea     rdx, [rbp+40h+TokenHandle]; void **
0x1800938c9  lea     rcx, [rbp+40h+var_C0]; this
0x1800938cd  call    ?Impersonate@CToken@@UEBAKPEAPEAX@Z; CToken::Impersonate(void * *)
0x1800938d2  mov     edi, eax
0x1800938d4  test    eax, eax
0x1800938d6  jnz     loc_180093AAC
0x1800938dc  xor     r8d, r8d
0x1800938df  mov     rdx, [rbp+40h+TokenHandle]
0x1800938e3  lea     rcx, [rbp+40h+arg_18]
0x1800938e7  call    cs:__imp_CreateEnvBlock
0x1800938ed  mov     edi, eax
0x1800938ef  lea     rdx, [rbp+40h+TokenHandle]; void **
0x1800938f3  lea     rcx, [rbp+40h+var_C0]; this
0x1800938f7  test    eax, eax
0x1800938f9  jns     loc_18009399E
0x1800938ff  call    ?Revert@CToken@@UEBAKPEAPEAX@Z; CToken::Revert(void * *)
0x180093904  mov     r8d, eax
0x180093907  test    eax, eax
0x180093909  jz      short loc_180093951
0x18009390b  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180093911  jz      short loc_180093951
0x180093913  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009391a  test    rax, rax
0x18009391d  jz      short loc_180093930
0x18009391f  lea     rdx, aFailedToRevert; "Failed to revert back user impersonatio"...
0x180093926  mov     ecx, r14d
0x180093929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009392e  jmp     short loc_180093951
0x180093930  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180093937  jz      short loc_180093951
0x180093939  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093940  jz      short loc_180093951
0x180093942  lea     rdx, aFailedToRevert; "Failed to revert back user impersonatio"...
0x180093949  mov     ecx, r14d; unsigned int
0x18009394c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093951  movzx   edi, di
0x180093954  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18009395a  jz      loc_180093AF9
0x180093960  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093967  test    rax, rax
0x18009396a  jz      short loc_180093978
0x18009396c  lea     rdx, aFailedToCreate_0; "Failed to create environment block = 0x"...
0x180093973  jmp     loc_180093AC7
0x180093978  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18009397f  jz      loc_180093AF9
0x180093985  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009398c  jz      loc_180093AF9
0x180093992  lea     rdx, aFailedToCreate_0; "Failed to create environment block = 0x"...
0x180093999  jmp     loc_180093AED
0x18009399e  call    ?Revert@CToken@@UEBAKPEAPEAX@Z; CToken::Revert(void * *)
0x1800939a3  test    eax, eax
0x1800939a5  jz      short loc_1800939F7
0x1800939a7  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800939ad  jz      short loc_1800939F7
0x1800939af  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800939b6  test    r9, r9
0x1800939b9  jz      short loc_1800939D2
0x1800939bb  mov     r8d, eax
0x1800939be  lea     rdx, aFailedToRevert; "Failed to revert back user impersonatio"...
0x1800939c5  mov     ecx, r14d
0x1800939c8  mov     rax, r9
0x1800939cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800939d0  jmp     short loc_1800939F7
0x1800939d2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800939d9  jz      short loc_1800939F7
0x1800939db  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800939e2  jz      short loc_1800939F7
0x1800939e4  mov     r8d, eax
0x1800939e7  lea     rdx, aFailedToRevert; "Failed to revert back user impersonatio"...
0x1800939ee  mov     ecx, r14d; unsigned int
0x1800939f1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800939f6  nop
0x1800939f7  mov     rax, [rbp+40h+arg_18]
0x1800939fb  lea     rcx, [rbp+40h+ProcessInformation]
0x1800939ff  mov     [rsp+140h+lpProcessInformation], rcx; lpProcessInformation
0x180093a04  lea     rcx, [rbp+40h+StartupInfo]
0x180093a08  mov     [rsp+140h+lpStartupInfo], rcx; lpStartupInfo
0x180093a0d  mov     [rsp+140h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x180093a12  mov     [rsp+140h+lpEnvironment], rax; lpEnvironment
0x180093a17  mov     [rsp+140h+dwCreationFlags], 400h; dwCreationFlags
0x180093a1f  mov     dword ptr [rsp+140h+phNewToken], esi; bInheritHandles
0x180093a23  mov     qword ptr [rsp+140h+TokenType], rsi; lpThreadAttributes
0x180093a28  xor     r9d, r9d; lpProcessAttributes
0x180093a2b  mov     r8, rbx; lpCommandLine
0x180093a2e  xor     edx, edx; lpApplicationName
0x180093a30  mov     rcx, [rbp+40h+TokenHandle]; hToken
0x180093a34  call    cs:__imp_CreateProcessAsUserW
0x180093a3a  test    eax, eax
0x180093a3c  jnz     short loc_180093A8C
0x180093a3e  call    cs:__imp_GetLastError
0x180093a44  mov     edi, eax
0x180093a46  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180093a4c  jz      loc_180093AF9
0x180093a52  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093a59  test    rax, rax
0x180093a5c  jz      short loc_180093A6A
0x180093a5e  lea     rdx, aFailedInCreate; "Failed in CreateProcessAsUser = 0x%x"
0x180093a65  jmp     loc_1800937F5
0x180093a6a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180093a71  jz      loc_180093AF9
0x180093a77  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093a7e  jz      short loc_180093AF9
0x180093a80  lea     rdx, aFailedInCreate; "Failed in CreateProcessAsUser = 0x%x"
0x180093a87  jmp     loc_180093826
0x180093a8c  mov     rdx, [rbp+40h+ProcessInformation.hThread]
0x180093a90  lea     rcx, [rsp+140h+var_D0]
0x180093a95  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x180093a9a  mov     rdx, [rbp+40h+ProcessInformation.hProcess]
0x180093a9e  lea     rcx, [rsp+140h+var_D8]
0x180093aa3  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x180093aa8  mov     edi, esi
0x180093aaa  jmp     short loc_180093AF9
0x180093aac  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180093ab2  jz      short loc_180093AF9
0x180093ab4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093abb  test    rax, rax
0x180093abe  jz      short loc_180093AD4
0x180093ac0  lea     rdx, aFailedToImpers_0; "Failed to impersonate user with error ="...
0x180093ac7  mov     r8d, edi
0x180093aca  mov     ecx, r14d
0x180093acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ad2  jmp     short loc_180093AF9
0x180093ad4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180093adb  jz      short loc_180093AF9
0x180093add  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093ae4  jz      short loc_180093AF9
0x180093ae6  lea     rdx, aFailedToImpers_0; "Failed to impersonate user with error ="...
0x180093aed  mov     r8d, edi
0x180093af0  mov     ecx, r14d; unsigned int
0x180093af3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093af8  nop
0x180093af9  mov     rcx, [rbp+40h+arg_18]
0x180093afd  test    rcx, rcx
0x180093b00  jz      short loc_180093B09
0x180093b02  call    cs:__imp_DestroyEnvBlock
0x180093b08  nop
0x180093b09  lea     rcx, [rsp+140h+var_D8]; this
0x180093b0e  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180093b13  nop
0x180093b14  lea     rcx, [rsp+140h+var_D0]; this
0x180093b19  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180093b1e  nop
0x180093b1f  lea     rcx, [rsp+140h+var_C8]; this
0x180093b24  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180093b29  nop
0x180093b2a  lea     rcx, [rsp+140h+lpCommandLine]
0x180093b2f  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180093b34  mov     eax, edi
  ... truncated ...
```

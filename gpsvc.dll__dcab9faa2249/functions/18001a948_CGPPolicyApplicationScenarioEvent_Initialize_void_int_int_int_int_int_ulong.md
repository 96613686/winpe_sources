# CGPPolicyApplicationScenarioEvent::Initialize(void *,int,int,int,int,int,ulong)

- ea: `0x18001a948`
- end: `0x18001ae38`
- name: `?Initialize@CGPPolicyApplicationScenarioEvent@@QEAAXPEAXHHHHHK@Z`
- size: `1264`
- prototype: `void(CGPPolicyApplicationScenarioEvent *__hidden this, void *, int, int, int, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f880`

## callees

- `0x18001a948`
- `0x18001ae40`
- `0x18001ae60`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001aae8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001aae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae10`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001aa29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001aa29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001aa0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001aa0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001aa6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001aa6a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001ab4c`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001ab4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae1b`
- `RPCRT4!UuidCreate` at `0x18001a985`
- `RPCRT4!UuidCreate` at `0x18001a985`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001aa4c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001aa4c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ae05`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ae05`
- `ntdll!EtwEventActivityIdControl` at `0x18001a9a5`
- `ntdll!EtwEventActivityIdControl` at `0x18001a9a5`
- `SspiCli!GetUserNameExW` at `0x18001aacf`
- `SspiCli!GetUserNameExW` at `0x18001aacf`

## string_xrefs

- `0x18001acb8`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x18001acdb`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x18001ad18`: `ImpersonateUser: Failed to impersonate user with %d.`
- `0x18001ad54`: `ImpersonateUser: Failed to impersonate user with %d.`
- `0x18001ac0f`: `Failed to create a unique activity id with error 0x%x`
- `0x18001ac3d`: `Failed to create a unique activity id with error 0x%x`
- `0x18001aba3`: `Failed to impersonate the user with 0x%x`
- `0x18001ad90`: `Failed to impersonate the user with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CGPPolicyApplicationScenarioEvent::Initialize(
        CGPPolicyApplicationScenarioEvent *this,
        void *a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        unsigned int a8)
{
  _OWORD *v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // r14d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  WCHAR *v19; // rdi
  int v20; // esi
  DWORD v21; // ebx
  WCHAR *v22; // rax
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v24; // eax
  void (*v25)(unsigned int, const unsigned __int16 *, ...); // rbx
  const wchar_t *v26; // rdx
  DWORD v27; // eax
  DWORD v28; // eax
  ULONG nSize; // [rsp+20h] [rbp-99h] BYREF
  void *TokenHandle[2]; // [rsp+28h] [rbp-91h] BYREF
  void *v31[5]; // [rsp+38h] [rbp-81h] BYREF
  int v32; // [rsp+64h] [rbp-55h]
  int v33; // [rsp+68h] [rbp-51h]
  int v34; // [rsp+88h] [rbp-31h]
  __int64 v35; // [rsp+A8h] [rbp-11h]

  v12 = (_OWORD *)((char *)this + 68);
  v13 = UuidCreate((UUID *)((char *)this + 68));
  if ( v13 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"Failed to create a unique activity id with error 0x%x", v13);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"Failed to create a unique activity id with error 0x%x", v13);
    }
  }
  v14 = EtwEventActivityIdControl(2, v12);
  if ( v14 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Failed to set the activity id with error 0x%x", v14);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Failed to set the activity id with error 0x%x", v14);
      }
    }
  }
  else
  {
    v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    *(_OWORD *)(v15 + 16) = *v12;
    *(_BYTE *)(v15 + 8) = 1;
  }
  *((_DWORD *)this + 21) = a3;
  *((_DWORD *)this + 22) = a4;
  *((_DWORD *)this + 23) = a5;
  *((_DWORD *)this + 24) = a6;
  *((_DWORD *)this + 25) = a7;
  *((_DWORD *)this + 26) = a8;
  TokenHandle[0] = 0;
  v16 = 0;
  if ( a3 )
    goto LABEL_8;
  CurrentThread = GetCurrentThread();
  v16 = 1;
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, TokenHandle) )
  {
    TokenHandle[0] = 0;
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_22;
      v25 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(4u, L"ImpersonateUser: Failed to open thread token with %d.", LastError);
        goto LABEL_22;
      }
      v26 = L"ImpersonateUser: Failed to open thread token with %d.";
LABEL_50:
      v25(4u, v26, LastError);
LABEL_22:
      v19 = 0;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v23 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v24 = GetLastError();
          v23(2u, L"Failed to impersonate the user with 0x%x", v24);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v28 = GetLastError();
          RedirectDebugMsg(2u, L"Failed to impersonate the user with 0x%x", v28);
        }
      }
      goto LABEL_15;
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
      goto LABEL_22;
    v25 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v27 = GetLastError();
        RedirectDebugMsg(4u, L"ImpersonateUser: Failed to impersonate user with %d.", v27);
      }
      goto LABEL_22;
    }
    LastError = GetLastError();
    v26 = L"ImpersonateUser: Failed to impersonate user with %d.";
    goto LABEL_50;
  }
LABEL_8:
  nSize = 75;
  v19 = (WCHAR *)LocalAlloc(0x40u, 0x96u);
  if ( !v19 )
  {
    v21 = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"MyGetUserName:  Failed to allocate memory with %d", v21);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"MyGetUserName:  Failed to allocate memory with %d", v21);
      }
    }
    goto LABEL_13;
  }
  v20 = 0;
  while ( 1 )
  {
    v31[0] = 0;
    v31[1] = 0;
    v31[2] = API_CALL_TRACING_END_SUCCESS;
    v31[3] = 0;
    v31[4] = "i\x1B";
    TokenHandle[1] = &CAPICallScenarioEvent::`vftable';
    v32 = 0;
    v33 = 4117;
    v34 = 4118;
    v35 = 0;
    if ( GetUserNameExW(NameSamCompatible, v19, &nSize) )
    {
      v21 = 0;
      goto LABEL_12;
    }
    v21 = GetLastError();
    if ( nSize )
    {
      if ( v21 == 122 || v21 == 234 )
        break;
    }
    switch ( v21 )
    {
      case 0x534u:
        goto LABEL_67;
      case 0x4CFu:
        goto LABEL_67;
      case 0x54Bu:
        goto LABEL_67;
    }
    if ( (unsigned int)++v20 > 3 )
      goto LABEL_67;
    Sleep(0x1F4u);
LABEL_20:
    CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(v31);
  }
  v22 = (WCHAR *)LocalReAlloc(v19, 2LL * nSize, 2u);
  if ( v22 )
  {
    v19 = v22;
    goto LABEL_20;
  }
  v21 = GetLastError();
LABEL_67:
  LocalFree(v19);
  v19 = 0;
LABEL_12:
  CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(v31);
LABEL_13:
  SetLastError(v21);
  if ( v16 )
    RevertToUser(TokenHandle);
LABEL_15:
  *((_QWORD *)this + 7) = v19;
}

```

## disassembly

```asm
0x18001a948  mov     [rsp-8+arg_10], rbx
0x18001a94d  push    rbp
0x18001a94e  push    rsi
0x18001a94f  push    rdi
0x18001a950  push    r12
0x18001a952  push    r13
0x18001a954  push    r14
0x18001a956  push    r15
0x18001a958  lea     rbp, [rsp-7]
0x18001a95d  sub     rsp, 0C0h
0x18001a964  mov     rax, cs:__security_cookie
0x18001a96b  xor     rax, rsp
0x18001a96e  mov     [rbp+37h+var_40], rax
0x18001a972  mov     r14d, r9d
0x18001a975  mov     edi, r8d
0x18001a978  mov     rsi, rdx
0x18001a97b  mov     r15, rcx
0x18001a97e  lea     rbx, [rcx+44h]
0x18001a982  mov     rcx, rbx; Uuid
0x18001a985  call    cs:__imp_UuidCreate
0x18001a98b  mov     r8d, eax
0x18001a98e  mov     r13d, 2
0x18001a994  xor     r12d, r12d
0x18001a997  test    eax, eax
0x18001a999  jnz     loc_18001ABF6
0x18001a99f  mov     rdx, rbx
0x18001a9a2  mov     ecx, r13d
0x18001a9a5  call    cs:__imp_EtwEventActivityIdControl
0x18001a9ab  mov     r8d, eax
0x18001a9ae  test    eax, eax
0x18001a9b0  jnz     loc_18001AC51
0x18001a9b6  mov     ecx, cs:_tls_index
0x18001a9bc  mov     rax, gs:58h
0x18001a9c5  mov     rdx, [rax+rcx*8]
0x18001a9c9  mov     eax, 10h
0x18001a9ce  movups  xmm0, xmmword ptr [rbx]
0x18001a9d1  movdqu  xmmword ptr [rax+rdx], xmm0
0x18001a9d6  mov     eax, 8
0x18001a9db  mov     byte ptr [rax+rdx], 1
0x18001a9df  mov     [r15+54h], edi
0x18001a9e3  mov     [r15+58h], r14d
0x18001a9e7  mov     eax, [rbp+37h+arg_20]
0x18001a9ea  mov     [r15+5Ch], eax
0x18001a9ee  mov     eax, [rbp+37h+arg_28]
0x18001a9f1  mov     [r15+60h], eax
0x18001a9f5  mov     eax, [rbp+37h+arg_30]
0x18001a9f8  mov     [r15+64h], eax
0x18001a9fc  mov     eax, [rbp+37h+arg_38]
0x18001a9ff  mov     [r15+68h], eax
0x18001aa03  mov     [rsp+0F0h+TokenHandle], r12
0x18001aa08  mov     r14d, r12d
0x18001aa0b  test    edi, edi
0x18001aa0d  jnz     short loc_18001AA5A
0x18001aa0f  call    cs:__imp_GetCurrentThread
0x18001aa15  mov     rcx, rax; ThreadHandle
0x18001aa18  lea     r9, [rsp+0F0h+TokenHandle]; TokenHandle
0x18001aa1d  lea     r14d, [rdi+1]
0x18001aa21  mov     r8d, r14d; OpenAsSelf
0x18001aa24  mov     edx, 2000Ch; DesiredAccess
0x18001aa29  call    cs:__imp_OpenThreadToken
0x18001aa2f  test    eax, eax
0x18001aa31  jnz     short loc_18001AA49
0x18001aa33  mov     [rsp+0F0h+TokenHandle], r12
0x18001aa38  call    cs:__imp_GetLastError
0x18001aa3e  cmp     eax, 3F0h
0x18001aa43  jnz     loc_18001AB6D
0x18001aa49  mov     rcx, rsi; hToken
0x18001aa4c  call    cs:__imp_ImpersonateLoggedOnUser
0x18001aa52  test    eax, eax
0x18001aa54  jz      loc_18001ACE4
0x18001aa5a  mov     [rsp+0F0h+nSize], 4Bh ; 'K'
0x18001aa62  mov     edx, 96h; uBytes
0x18001aa67  lea     ecx, [rdx-56h]; uFlags
0x18001aa6a  call    cs:__imp_LocalAlloc
0x18001aa70  mov     rdi, rax
0x18001aa73  test    rax, rax
0x18001aa76  jz      loc_18001ABBA
0x18001aa7c  mov     esi, r12d
0x18001aa7f  mov     [rsp+0F0h+var_B8], r12
0x18001aa84  mov     [rbp+37h+var_B0], r12
0x18001aa88  lea     rax, API_CALL_TRACING_END_SUCCESS
0x18001aa8f  mov     [rbp+37h+var_A8], rax
0x18001aa93  mov     [rbp+37h+var_A0], r12
0x18001aa97  lea     rax, API_CALL_TRACING_END_FAILURE; "i\x1B"
0x18001aa9e  mov     [rbp+37h+var_98], rax
0x18001aaa2  lea     rax, ??_7CAPICallScenarioEvent@@6B@; const CAPICallScenarioEvent::`vftable'
0x18001aaa9  mov     [rsp+0F0h+var_C0], rax
0x18001aaae  mov     [rbp+37h+var_8C], r12d
0x18001aab2  mov     [rbp+37h+var_88], 1015h
0x18001aab9  mov     [rbp+37h+var_68], 1016h
0x18001aac0  mov     [rbp+37h+var_48], r12
0x18001aac4  lea     r8, [rsp+0F0h+nSize]; nSize
0x18001aac9  mov     rdx, rdi; lpNameBuffer
0x18001aacc  mov     ecx, r13d; NameFormat
0x18001aacf  call    cs:__imp_GetUserNameExW
0x18001aad5  test    al, al
0x18001aad7  jz      short loc_18001AB22
0x18001aad9  mov     ebx, r12d
0x18001aadc  lea     rcx, [rsp+0F0h+var_B8]; this
0x18001aae1  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x18001aae6  mov     ecx, ebx; dwErrCode
0x18001aae8  call    cs:__imp_SetLastError
0x18001aaee  test    r14d, r14d
0x18001aaf1  jnz     loc_18001AE29
0x18001aaf7  mov     [r15+38h], rdi
0x18001aafb  mov     rcx, [rbp+37h+var_40]
0x18001aaff  xor     rcx, rsp; StackCookie
0x18001ab02  call    __security_check_cookie
0x18001ab07  mov     rbx, [rsp+0F0h+arg_10]
0x18001ab0f  add     rsp, 0C0h
0x18001ab16  pop     r15
0x18001ab18  pop     r14
0x18001ab1a  pop     r13
0x18001ab1c  pop     r12
0x18001ab1e  pop     rdi
0x18001ab1f  pop     rsi
0x18001ab20  pop     rbp
0x18001ab21  retn
0x18001ab22  call    cs:__imp_GetLastError
0x18001ab28  nop
0x18001ab29  mov     ebx, eax
0x18001ab2b  mov     eax, [rsp+0F0h+nSize]
0x18001ab2f  test    eax, eax
0x18001ab31  jz      loc_18001ADE1
0x18001ab37  cmp     ebx, 7Ah ; 'z'
0x18001ab3a  jnz     loc_18001ADD5
0x18001ab40  mov     rdx, rax
0x18001ab43  add     rdx, rdx; uBytes
0x18001ab46  mov     r8d, r13d; uFlags
0x18001ab49  mov     rcx, rdi; hMem
0x18001ab4c  call    cs:__imp_LocalReAlloc
0x18001ab52  test    rax, rax
0x18001ab55  jz      loc_18001AE10
0x18001ab5b  mov     rdi, rax
0x18001ab5e  lea     rcx, [rsp+0F0h+var_B8]; this
0x18001ab63  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x18001ab68  jmp     loc_18001AA7F
0x18001ab6d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001ab74  jnz     loc_18001ACAC
0x18001ab7a  mov     rdi, r12
0x18001ab7d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001ab84  jz      loc_18001AAF7
0x18001ab8a  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001ab91  test    rbx, rbx
0x18001ab94  jz      loc_18001AD6D
0x18001ab9a  call    cs:__imp_GetLastError
0x18001aba0  mov     r8d, eax
0x18001aba3  lea     rdx, aFailedToImpers_1; "Failed to impersonate the user with 0x%"...
0x18001abaa  mov     ecx, r13d
0x18001abad  mov     rax, rbx
0x18001abb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abb5  jmp     loc_18001AAF7
0x18001abba  call    cs:__imp_GetLastError
0x18001abc0  mov     ebx, eax
0x18001abc2  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001abc9  jz      loc_18001AAE6
0x18001abcf  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001abd6  test    rax, rax
0x18001abd9  jz      loc_18001ADA4
0x18001abdf  mov     r8d, ebx
0x18001abe2  lea     rdx, aMygetusernameF; "MyGetUserName:  Failed to allocate memo"...
0x18001abe9  mov     ecx, r13d
0x18001abec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abf1  jmp     loc_18001AAE6
0x18001abf6  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001abfd  jz      loc_18001A99F
0x18001ac03  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001ac0a  test    rax, rax
0x18001ac0d  jz      short loc_18001AC23
0x18001ac0f  lea     rdx, aFailedToCreate; "Failed to create a unique activity id w"...
0x18001ac16  mov     ecx, r13d
0x18001ac19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac1e  jmp     loc_18001A99F
0x18001ac23  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001ac2a  jz      loc_18001A99F
0x18001ac30  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001ac37  jz      loc_18001A99F
0x18001ac3d  lea     rdx, aFailedToCreate; "Failed to create a unique activity id w"...
0x18001ac44  mov     ecx, r13d; unsigned int
0x18001ac47  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001ac4c  jmp     loc_18001A99F
0x18001ac51  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001ac58  jz      loc_18001A9DF
0x18001ac5e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001ac65  test    rax, rax
0x18001ac68  jz      short loc_18001AC7E
0x18001ac6a  lea     rdx, aFailedToSetThe; "Failed to set the activity id with erro"...
0x18001ac71  mov     ecx, r13d
0x18001ac74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac79  jmp     loc_18001A9DF
0x18001ac7e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001ac85  jz      loc_18001A9DF
0x18001ac8b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001ac92  jz      loc_18001A9DF
0x18001ac98  lea     rdx, aFailedToSetThe; "Failed to set the activity id with erro"...
0x18001ac9f  mov     ecx, r13d; unsigned int
0x18001aca2  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001aca7  jmp     loc_18001A9DF
0x18001acac  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001acb3  test    rbx, rbx
0x18001acb6  jz      short loc_18001ACC1
0x18001acb8  lea     rdx, aImpersonateuse; "ImpersonateUser: Failed to open thread "...
0x18001acbf  jmp     short loc_18001AD1F
0x18001acc1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001acc8  jz      loc_18001AB7A
0x18001acce  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001acd5  jz      loc_18001AB7A
0x18001acdb  lea     rdx, aImpersonateuse; "ImpersonateUser: Failed to open thread "...
0x18001ace2  jmp     short loc_18001AD5B
0x18001ace4  mov     rcx, [rsp+0F0h+TokenHandle]; hObject
0x18001ace9  test    rcx, rcx
0x18001acec  jz      short loc_18001ACF9
0x18001acee  call    cs:__imp_CloseHandle
0x18001acf4  mov     [rsp+0F0h+TokenHandle], r12
0x18001acf9  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001ad00  jz      loc_18001AB7A
0x18001ad06  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001ad0d  test    rbx, rbx
0x18001ad10  jz      short loc_18001AD34
0x18001ad12  call    cs:__imp_GetLastError
0x18001ad18  lea     rdx, aImpersonateuse_0; "ImpersonateUser: Failed to impersonate "...
0x18001ad1f  mov     r8d, eax
0x18001ad22  mov     ecx, 4
0x18001ad27  mov     rax, rbx
0x18001ad2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad2f  jmp     loc_18001AB7A
0x18001ad34  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001ad3b  jz      loc_18001AB7A
0x18001ad41  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001ad48  jz      loc_18001AB7A
0x18001ad4e  call    cs:__imp_GetLastError
0x18001ad54  lea     rdx, aImpersonateuse_0; "ImpersonateUser: Failed to impersonate "...
0x18001ad5b  mov     r8d, eax
0x18001ad5e  mov     ecx, 4; unsigned int
0x18001ad63  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001ad68  jmp     loc_18001AB7A
0x18001ad6d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001ad74  jz      loc_18001AAF7
0x18001ad7a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001ad81  jz      loc_18001AAF7
0x18001ad87  call    cs:__imp_GetLastError
0x18001ad8d  mov     r8d, eax
0x18001ad90  lea     rdx, aFailedToImpers_1; "Failed to impersonate the user with 0x%"...
0x18001ad97  mov     ecx, r13d; unsigned int
0x18001ad9a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001ad9f  jmp     loc_18001AAF7
0x18001ada4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001adab  jz      loc_18001AAE6
0x18001adb1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001adb8  jz      loc_18001AAE6
0x18001adbe  mov     r8d, ebx
0x18001adc1  lea     rdx, aMygetusernameF; "MyGetUserName:  Failed to allocate memo"...
0x18001adc8  mov     ecx, r13d; unsigned int
0x18001adcb  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001add0  jmp     loc_18001AAE6
0x18001add5  cmp     ebx, 0EAh
0x18001addb  jz      loc_18001AB40
0x18001ade1  cmp     ebx, 534h
0x18001ade7  jz      short loc_18001AE18
0x18001ade9  cmp     ebx, 4CFh
0x18001adef  jz      short loc_18001AE18
0x18001adf1  cmp     ebx, 54Bh
0x18001adf7  jz      short loc_18001AE18
0x18001adf9  inc     esi
0x18001adfb  cmp     esi, 3
0x18001adfe  ja      short loc_18001AE18
0x18001ae00  mov     ecx, 1F4h; dwMilliseconds
0x18001ae05  call    cs:__imp_Sleep
0x18001ae0b  jmp     loc_18001AB5E
0x18001ae10  call    cs:__imp_GetLastError
0x18001ae16  mov     ebx, eax
0x18001ae18  mov     rcx, rdi; hMem
0x18001ae1b  call    cs:__imp_LocalFree
0x18001ae21  mov     rdi, r12
0x18001ae24  jmp     loc_18001AADC
0x18001ae29  lea     rcx, [rsp+0F0h+TokenHandle]; void **
0x18001ae2e  call    ?RevertToUser@@YAHPEAPEAX@Z; RevertToUser(void * *)
0x18001ae33  jmp     loc_18001AAF7
```

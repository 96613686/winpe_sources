# _lambda_b41eca68381dbaccfa3ca70d9f77ac5d_::operator()

- ea: `0x180003090`
- end: `0x1800032f2`
- name: `_lambda_b41eca68381dbaccfa3ca70d9f77ac5d_::operator()`
- size: `610`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800029d0`
- `0x180002f14`

## callees

- `0x180003090`
- `0x18000547c`
- `0x180005558`
- `0x1800055c8`
- `0x180006a9c`
- `0x18000f9c8`
- `0x18001044c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003242`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800030c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800030c9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800031e3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800032a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800031e3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800032a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800030e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800030e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003269`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003269`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032b0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000311d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000311d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800031cd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003216`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800032d4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800031cd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003216`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800032d4`
- `ntdll!RtlAdjustPrivilege` at `0x180003193`
- `ntdll!RtlAdjustPrivilege` at `0x180003193`
- `USERENV!GetProfileType` at `0x18000313a`
- `USERENV!GetProfileType` at `0x18000313a`
- `RPCRT4!RpcRevertToSelf` at `0x180003206`
- `RPCRT4!RpcRevertToSelf` at `0x1800032c4`
- `RPCRT4!RpcRevertToSelf` at `0x180003206`
- `RPCRT4!RpcRevertToSelf` at `0x1800032c4`

## string_xrefs

- `0x18000314c`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x18000327a`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_b41eca68381dbaccfa3ca70d9f77ac5d_::operator()(__int64 a1)
{
  void *v2; // rdi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  unsigned int v7; // edx
  unsigned int v8; // edi
  __int64 v9; // r10
  NTSTATUS v10; // eax
  signed int v12; // eax
  HANDLE v13; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  __int64 v15; // [rsp+30h] [rbp-20h]
  unsigned int v16; // [rsp+38h] [rbp-18h]
  void *lpMem[2]; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned __int8 OldValue; // [rsp+70h] [rbp+20h] BYREF
  DWORD dwFlags; // [rsp+78h] [rbp+28h] BYREF

  LODWORD(v13) = 0;
  TokenHandle = 0;
  v15 = 0;
  v16 = 0;
  *(_OWORD *)lpMem = 0;
  v2 = **(void ***)a1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
    {
      v5 = -2147467259;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11E,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
        (const char *)v5);
      CThreadContext::RevertPrivileges((CThreadContext *)&v13);
      if ( (_DWORD)v13 )
      {
        SetThreadToken(0, TokenHandle);
        if ( TokenHandle )
        {
          CloseHandle(TokenHandle);
          TokenHandle = 0;
        }
        LODWORD(v13) = 0;
      }
      if ( HIDWORD(v15) )
      {
        RpcRevertToSelf();
        HIDWORD(v15) = 0;
      }
      if ( (_DWORD)v15 )
        RevertToSelf();
      return v5;
    }
    if ( v5 != -2147023888 )
      goto LABEL_33;
  }
  if ( !ImpersonateLoggedOnUser(v2) )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    v5 = v12;
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    goto LABEL_33;
  }
  LODWORD(v13) = 1;
  dwFlags = 0;
  if ( !GetProfileType(&dwFlags) )
  {
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x121,
           (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
           v6);
    OldValue = 0;
    v7 = v16;
    if ( v16 )
    {
      v8 = 0;
      do
      {
        v9 = 4LL * v8;
        if ( *(_DWORD *)((char *)lpMem[1] + v9) )
        {
          v10 = RtlAdjustPrivilege(*(_DWORD *)((char *)lpMem[0] + v9), 0, 1u, &OldValue);
          ResultFromWin32FromStatus(v10);
          v7 = v16;
        }
        ++v8;
      }
      while ( v8 < v7 );
      ResultFromHeapFree(lpMem[0]);
      lpMem[0] = 0;
      ResultFromHeapFree(lpMem[1]);
      lpMem[1] = 0;
      v16 = 0;
    }
    if ( (_DWORD)v15 )
    {
      RevertToSelf();
      LODWORD(v15) = 0;
    }
    SetThreadToken(0, TokenHandle);
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    LODWORD(v13) = 0;
    if ( HIDWORD(v15) )
    {
      RpcRevertToSelf();
      HIDWORD(v15) = 0;
    }
    if ( (_DWORD)v15 )
      RevertToSelf();
    return v5;
  }
  if ( (dwFlags & 2) != 0 )
    **(_DWORD **)(a1 + 8) = 1;
  CThreadContext::~CThreadContext(&v13);
  return 0;
}

```

## disassembly

```asm
0x180003090  mov     [rsp-18h+arg_10], rbx
0x180003095  mov     [rsp-18h+arg_18], rsi
0x18000309a  push    rbp
0x18000309b  push    rdi
0x18000309c  push    r14
0x18000309e  mov     rbp, rsp
0x1800030a1  sub     rsp, 50h
0x1800030a5  mov     rsi, rcx
0x1800030a8  xor     r14d, r14d
0x1800030ab  mov     dword ptr [rbp+var_30], r14d
0x1800030af  mov     [rbp+TokenHandle], r14
0x1800030b3  mov     [rbp+var_20], r14
0x1800030b7  mov     [rbp+var_18], r14d
0x1800030bb  xorps   xmm0, xmm0
0x1800030be  movdqu  xmmword ptr [rbp+lpMem], xmm0
0x1800030c3  mov     rax, [rcx]
0x1800030c6  mov     rdi, [rax]
0x1800030c9  call    cs:__imp_GetCurrentThread
0x1800030cf  mov     rcx, rax; ThreadHandle
0x1800030d2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800030d6  mov     edx, 2000Ch; DesiredAccess
0x1800030db  mov     r8d, 1; OpenAsSelf
0x1800030e1  call    cs:__imp_OpenThreadToken
0x1800030e7  test    eax, eax
0x1800030e9  jnz     short loc_18000311A
0x1800030eb  call    cs:__imp_GetLastError
0x1800030f1  mov     ebx, eax
0x1800030f3  test    eax, eax
0x1800030f5  jle     short loc_180003100
0x1800030f7  movzx   ebx, ax
0x1800030fa  or      ebx, 80070000h
0x180003100  test    ebx, ebx
0x180003102  js      short loc_18000310E
0x180003104  mov     ebx, 80004005h
0x180003109  jmp     loc_180003273
0x18000310e  cmp     ebx, 800703F0h
0x180003114  jnz     loc_180003273
0x18000311a  mov     rcx, rdi; hToken
0x18000311d  call    cs:__imp_ImpersonateLoggedOnUser
0x180003123  test    eax, eax
0x180003125  jz      loc_180003242
0x18000312b  mov     dword ptr [rbp+var_30], 1
0x180003132  mov     [rbp+dwFlags], r14d
0x180003136  lea     rcx, [rbp+dwFlags]; dwFlags
0x18000313a  call    cs:__imp_GetProfileType
0x180003140  test    eax, eax
0x180003142  jnz     loc_180003222
0x180003148  mov     rcx, [rbp+18h]; this
0x18000314c  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180003153  mov     edx, 121h; void *
0x180003158  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000315d  mov     ebx, eax
0x18000315f  mov     [rbp+OldValue], 0
0x180003163  mov     edx, [rbp+var_18]
0x180003166  test    edx, edx
0x180003168  jz      short loc_1800031C7
0x18000316a  mov     edi, r14d
0x18000316d  mov     eax, edi
0x18000316f  lea     r10, ds:0[rax*4]
0x180003177  mov     rax, [rbp+lpMem+8]
0x18000317b  cmp     dword ptr [r10+rax], 0
0x180003180  jz      short loc_1800031A3
0x180003182  lea     r9, [rbp+OldValue]; OldValue
0x180003186  mov     r8b, 1; ForThread
0x180003189  xor     edx, edx; NewValue
0x18000318b  mov     rcx, [rbp+lpMem]
0x18000318f  mov     ecx, [r10+rcx]; Privilege
0x180003193  call    cs:__imp_RtlAdjustPrivilege
0x180003199  mov     ecx, eax; int
0x18000319b  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1800031a0  mov     edx, [rbp+var_18]
0x1800031a3  inc     edi
0x1800031a5  cmp     edi, edx
0x1800031a7  jb      short loc_18000316D
0x1800031a9  mov     rcx, [rbp+lpMem]; lpMem
0x1800031ad  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800031b2  mov     [rbp+lpMem], r14
0x1800031b6  mov     rcx, [rbp+lpMem+8]; lpMem
0x1800031ba  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800031bf  mov     [rbp+lpMem+8], r14
0x1800031c3  mov     [rbp+var_18], r14d
0x1800031c7  cmp     dword ptr [rbp+var_20], 0
0x1800031cb  jz      short loc_1800031D7
0x1800031cd  call    cs:__imp_RevertToSelf
0x1800031d3  mov     dword ptr [rbp+var_20], r14d
0x1800031d7  cmp     dword ptr [rbp+var_30], 0
0x1800031db  jz      short loc_180003200
0x1800031dd  mov     rdx, [rbp+TokenHandle]; Token
0x1800031e1  xor     ecx, ecx; Thread
0x1800031e3  call    cs:__imp_SetThreadToken
0x1800031e9  mov     rcx, [rbp+TokenHandle]; hObject
0x1800031ed  test    rcx, rcx
0x1800031f0  jz      short loc_1800031FC
0x1800031f2  call    cs:__imp_CloseHandle
0x1800031f8  mov     [rbp+TokenHandle], r14
0x1800031fc  mov     dword ptr [rbp+var_30], r14d
0x180003200  cmp     dword ptr [rbp+var_20+4], 0
0x180003204  jz      short loc_180003210
0x180003206  call    cs:__imp_RpcRevertToSelf
0x18000320c  mov     dword ptr [rbp+var_20+4], r14d
0x180003210  cmp     dword ptr [rbp+var_20], 0
0x180003214  jz      short loc_18000321D
0x180003216  call    cs:__imp_RevertToSelf
0x18000321c  nop
0x18000321d  jmp     loc_1800032DB
0x180003222  test    byte ptr [rbp+dwFlags], 2
0x180003226  jz      short loc_180003232
0x180003228  mov     rax, [rsi+8]
0x18000322c  mov     dword ptr [rax], 1
0x180003232  lea     rcx, [rbp+var_30]; this
0x180003236  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18000323b  xor     eax, eax
0x18000323d  jmp     loc_1800032DD
0x180003242  call    cs:__imp_GetLastError
0x180003248  test    eax, eax
0x18000324a  jle     short loc_180003254
0x18000324c  movzx   eax, ax
0x18000324f  or      eax, 80070000h
0x180003254  mov     ebx, 80004005h
0x180003259  test    eax, eax
0x18000325b  cmovns  eax, ebx
0x18000325e  mov     ebx, eax
0x180003260  mov     rcx, [rbp+TokenHandle]; hObject
0x180003264  test    rcx, rcx
0x180003267  jz      short loc_180003273
0x180003269  call    cs:__imp_CloseHandle
0x18000326f  mov     [rbp+TokenHandle], r14
0x180003273  mov     rcx, [rbp+18h]; this
0x180003277  mov     r9d, ebx; char *
0x18000327a  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180003281  mov     edx, 11Eh; void *
0x180003286  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000328b  nop
0x18000328c  lea     rcx, [rbp+var_30]; this
0x180003290  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180003295  cmp     dword ptr [rbp+var_30], 0
0x180003299  jz      short loc_1800032BE
0x18000329b  mov     rdx, [rbp+TokenHandle]; Token
0x18000329f  xor     ecx, ecx; Thread
0x1800032a1  call    cs:__imp_SetThreadToken
0x1800032a7  mov     rcx, [rbp+TokenHandle]; hObject
0x1800032ab  test    rcx, rcx
0x1800032ae  jz      short loc_1800032BA
0x1800032b0  call    cs:__imp_CloseHandle
0x1800032b6  mov     [rbp+TokenHandle], r14
0x1800032ba  mov     dword ptr [rbp+var_30], r14d
0x1800032be  cmp     dword ptr [rbp+var_20+4], 0
0x1800032c2  jz      short loc_1800032CE
0x1800032c4  call    cs:__imp_RpcRevertToSelf
0x1800032ca  mov     dword ptr [rbp+var_20+4], r14d
0x1800032ce  cmp     dword ptr [rbp+var_20], 0
0x1800032d2  jz      short loc_1800032DB
0x1800032d4  call    cs:__imp_RevertToSelf
0x1800032da  nop
0x1800032db  mov     eax, ebx
0x1800032dd  lea     r11, [rsp+50h+var_s0]
0x1800032e2  mov     rbx, [r11+30h]
0x1800032e6  mov     rsi, [r11+38h]
0x1800032ea  mov     rsp, r11
0x1800032ed  pop     r14
0x1800032ef  pop     rdi
0x1800032f0  pop     rbp
0x1800032f1  retn
```

# ImpersonateUser(void *,void * *)

- ea: `0x18005334c`
- end: `0x18005347a`
- name: `?ImpersonateUser@@YAHPEAXPEAPEAX@Z`
- size: `302`
- prototype: `__int64 __fastcall(HANDLE hToken, PHANDLE TokenHandle)`
- caller_count: `10`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005e4c`
- `0x18001bc88`
- `0x18001dd14`
- `0x180030bcc`
- `0x180058f20`
- `0x18005ce5c`
- `0x18009ac70`
- `0x18009ff54`
- `0x1800b2548`
- `0x1800b2d88`

## callees

- `0x18005334c`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005341d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005345b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005341d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005345b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053373`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053373`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005335c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005335c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800533fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800533fb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180053394`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180053394`

## string_xrefs

- `0x1800533ca`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x1800533ea`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x180053426`: `ImpersonateUser: Failed to impersonate user with %d.`
- `0x180053461`: `ImpersonateUser: Failed to impersonate user with %d.`

## pseudocode

```c
__int64 __fastcall ImpersonateUser(HANDLE hToken, PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  DWORD v5; // eax
  void (*v7)(unsigned int, const unsigned __int16 *, ...); // rbx
  __int64 LastError; // r8
  DWORD v9; // eax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, TokenHandle) || (*TokenHandle = 0, v5 = GetLastError(), v5 == 1008) )
  {
    if ( ImpersonateLoggedOnUser(hToken) )
      return 1;
    if ( *TokenHandle )
    {
      CloseHandle(*TokenHandle);
      *TokenHandle = 0;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v7 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        LastError = GetLastError();
        v7(4u, L"ImpersonateUser: Failed to impersonate user with %d.", LastError);
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
        {
          v9 = GetLastError();
          RedirectDebugMsg(4u, L"ImpersonateUser: Failed to impersonate user with %d.", v9);
        }
      }
    }
  }
  else if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ImpersonateUser: Failed to open thread token with %d.", v5);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ImpersonateUser: Failed to open thread token with %d.", v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005334c  mov     [rsp+arg_0], rbx
0x180053351  push    rdi
0x180053352  sub     rsp, 20h
0x180053356  mov     rbx, rdx
0x180053359  mov     rdi, rcx
0x18005335c  call    cs:__imp_GetCurrentThread
0x180053362  mov     r9, rbx; TokenHandle
0x180053365  mov     edx, 2000Ch; DesiredAccess
0x18005336a  mov     rcx, rax; ThreadHandle
0x18005336d  mov     r8d, 1; OpenAsSelf
0x180053373  call    cs:__imp_OpenThreadToken
0x180053379  test    eax, eax
0x18005337b  jnz     short loc_180053391
0x18005337d  mov     qword ptr [rbx], 0
0x180053384  call    cs:__imp_GetLastError
0x18005338a  cmp     eax, 3F0h
0x18005338f  jnz     short loc_1800533AE
0x180053391  mov     rcx, rdi; hToken
0x180053394  call    cs:__imp_ImpersonateLoggedOnUser
0x18005339a  test    eax, eax
0x18005339c  jz      short loc_1800533F3
0x18005339e  mov     eax, 1
0x1800533a3  mov     rbx, [rsp+28h+arg_0]
0x1800533a8  add     rsp, 20h
0x1800533ac  pop     rdi
0x1800533ad  retn
0x1800533ae  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800533b5  jnz     short loc_1800533BB
0x1800533b7  xor     eax, eax
0x1800533b9  jmp     short loc_1800533A3
0x1800533bb  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800533c2  test    r9, r9
0x1800533c5  jz      short loc_1800533D6
0x1800533c7  mov     r8d, eax
0x1800533ca  lea     rdx, aImpersonateuse; "ImpersonateUser: Failed to open thread "...
0x1800533d1  mov     rax, r9
0x1800533d4  jmp     short loc_180053430
0x1800533d6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800533de  jz      short loc_1800533B7
0x1800533e0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800533e8  jz      short loc_1800533B7
0x1800533ea  lea     rdx, aImpersonateuse; "ImpersonateUser: Failed to open thread "...
0x1800533f1  jmp     short loc_180053468
0x1800533f3  mov     rcx, [rbx]; hObject
0x1800533f6  test    rcx, rcx
0x1800533f9  jz      short loc_180053408
0x1800533fb  call    cs:__imp_CloseHandle
0x180053401  mov     qword ptr [rbx], 0
0x180053408  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18005340f  jz      short loc_1800533B7
0x180053411  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180053418  test    rbx, rbx
0x18005341b  jz      short loc_18005343F
0x18005341d  call    cs:__imp_GetLastError
0x180053423  mov     r8d, eax
0x180053426  lea     rdx, aImpersonateuse_0; "ImpersonateUser: Failed to impersonate "...
0x18005342d  mov     rax, rbx
0x180053430  mov     ecx, 4
0x180053435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005343a  jmp     loc_1800533B7
0x18005343f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180053447  jz      loc_1800533B7
0x18005344d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180053455  jz      loc_1800533B7
0x18005345b  call    cs:__imp_GetLastError
0x180053461  lea     rdx, aImpersonateuse_0; "ImpersonateUser: Failed to impersonate "...
0x180053468  mov     r8d, eax
0x18005346b  mov     ecx, 4; unsigned int
0x180053470  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180053475  jmp     loc_1800533B7
```

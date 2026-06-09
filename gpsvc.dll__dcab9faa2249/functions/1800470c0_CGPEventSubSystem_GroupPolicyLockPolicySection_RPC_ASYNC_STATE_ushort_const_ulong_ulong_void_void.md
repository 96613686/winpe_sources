# CGPEventSubSystem::GroupPolicyLockPolicySection(_RPC_ASYNC_STATE *,ushort const *,ulong,ulong,void *,void * *)

- ea: `0x1800470c0`
- end: `0x18004739f`
- name: `?GroupPolicyLockPolicySection@CGPEventSubSystem@@UEAAKPEAU_RPC_ASYNC_STATE@@PEBGKKPEAXPEAPEAX@Z`
- size: `735`
- prototype: `unsigned int __fastcall(CGPEventSubSystem *__hidden this, struct _RPC_ASYNC_STATE *, const unsigned __int16 *, unsigned int, unsigned int, void *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800470c0`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047327`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047127`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004710e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004710e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800471e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800471e7`
- `RPCRT4!RpcImpersonateClient` at `0x1800470fe`
- `RPCRT4!RpcImpersonateClient` at `0x1800470fe`
- `RPCRT4!RpcRevertToSelf` at `0x180047135`
- `RPCRT4!RpcRevertToSelf` at `0x180047135`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004717e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004717e`

## string_xrefs

- `0x180047214`: `Failed to Impersonate Client. Status = 0x%x`
- `0x18004723e`: `Failed to Impersonate Client. Status = 0x%x`
- `0x180047275`: `Failed to Get User's Token. Status = 0x%x`
- `0x1800472aa`: `Failed to Get User's Token. Status = 0x%x`
- `0x180047353`: `Failed to session from token. Status = 0x%x`
- `0x180047388`: `Failed to session from token. Status = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGPEventSubSystem::GroupPolicyLockPolicySection(
        CGPEventSubSystem *this,
        struct _RPC_ASYNC_STATE *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        void *a6,
        void **a7)
{
  int v11; // r10d
  void *v12; // r8
  unsigned int v13; // esi
  DWORD LastError; // edi
  HANDLE CurrentThread; // rax
  DWORD ReturnLength; // [rsp+50h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-40h] BYREF
  int TokenInformation; // [rsp+A8h] [rbp+10h] BYREF

  v11 = 0;
  TokenInformation = 0;
  v12 = 0;
  TokenHandle = 0;
  v13 = a5;
  if ( !a2 )
    goto LABEL_9;
  LastError = RpcImpersonateClient(0);
  if ( LastError )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Failed to Impersonate Client. Status = 0x%x", LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Failed to Impersonate Client. Status = 0x%x", LastError);
      }
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"Failed to Get User's Token. Status = 0x%x", LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"Failed to Get User's Token. Status = 0x%x", LastError);
        }
      }
    }
    if ( RpcRevertToSelf() && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"RpcRevertToSelf Failed. Status = 0x%x", LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"RpcRevertToSelf Failed. Status = 0x%x", LastError);
      }
    }
    if ( !LastError )
    {
      if ( (v13 & 0x10000000) != 0 )
      {
        ReturnLength = 0;
        TokenInformation = 0;
        if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
        {
          LastError = GetLastError();
          if ( LastError )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"Failed to session from token. Status = 0x%x", LastError);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"Failed to session from token. Status = 0x%x", LastError);
              }
            }
            goto LABEL_10;
          }
        }
      }
      v11 = TokenInformation;
      v12 = TokenHandle;
LABEL_9:
      LastError = (*(__int64 (__fastcall **)(_QWORD, struct _RPC_ASYNC_STATE *, void *, const unsigned __int16 *, int, int, unsigned int, void *, void **))(**((_QWORD **)this + 1) + 112LL))(
                    *((_QWORD *)this + 1),
                    a2,
                    v12,
                    a3,
                    v11,
                    a4,
                    v13,
                    a6,
                    a7);
    }
  }
LABEL_10:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800470c0  push    rbx
0x1800470c2  push    rbp
0x1800470c3  push    rsi
0x1800470c4  push    rdi
0x1800470c5  push    r14
0x1800470c7  push    r15
0x1800470c9  sub     rsp, 68h
0x1800470cd  mov     ebp, r9d
0x1800470d0  mov     r14, r8
0x1800470d3  mov     rbx, rdx
0x1800470d6  mov     r15, rcx
0x1800470d9  xor     r10d, r10d
0x1800470dc  mov     [rsp+98h+TokenInformation], r10d
0x1800470e4  xor     r8d, r8d
0x1800470e7  mov     [rsp+98h+TokenHandle], r8
0x1800470ec  mov     esi, [rsp+98h+arg_20]
0x1800470f3  test    rdx, rdx
0x1800470f6  jz      loc_180047199
0x1800470fc  xor     ecx, ecx; BindingHandle
0x1800470fe  call    cs:__imp_RpcImpersonateClient
0x180047104  mov     edi, eax
0x180047106  test    eax, eax
0x180047108  jnz     loc_1800471FC
0x18004710e  call    cs:__imp_GetCurrentThread
0x180047114  mov     rcx, rax; ThreadHandle
0x180047117  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x18004711c  mov     edx, 0Eh; DesiredAccess
0x180047121  mov     r8d, 1; OpenAsSelf
0x180047127  call    cs:__imp_OpenThreadToken
0x18004712d  test    eax, eax
0x18004712f  jz      loc_180047251
0x180047135  call    cs:__imp_RpcRevertToSelf
0x18004713b  test    eax, eax
0x18004713d  jnz     loc_1800472C0
0x180047143  test    edi, edi
0x180047145  jnz     loc_1800471D8
0x18004714b  bt      esi, 1Ch
0x18004714f  jnb     short loc_18004718C
0x180047151  mov     [rsp+98h+var_48], edi
0x180047155  mov     [rsp+98h+TokenInformation], edi
0x18004715c  lea     rax, [rsp+98h+var_48]
0x180047161  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180047166  mov     r9d, 4; TokenInformationLength
0x18004716c  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x180047174  mov     edx, 0Ch; TokenInformationClass
0x180047179  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x18004717e  call    cs:__imp_GetTokenInformation
0x180047184  test    eax, eax
0x180047186  jz      loc_180047327
0x18004718c  mov     r10d, [rsp+98h+TokenInformation]
0x180047194  mov     r8, [rsp+98h+TokenHandle]
0x180047199  mov     rcx, [r15+8]
0x18004719d  mov     rax, [rcx]
0x1800471a0  mov     rdx, [rsp+98h+arg_30]
0x1800471a8  mov     [rsp+98h+var_58], rdx
0x1800471ad  mov     rdx, [rsp+98h+arg_28]
0x1800471b5  mov     [rsp+98h+var_60], rdx
0x1800471ba  mov     [rsp+98h+var_68], esi
0x1800471be  mov     [rsp+98h+var_70], ebp
0x1800471c2  mov     dword ptr [rsp+98h+ReturnLength], r10d
0x1800471c7  mov     r9, r14
0x1800471ca  mov     rdx, rbx
0x1800471cd  mov     rax, [rax+70h]
0x1800471d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471d6  mov     edi, eax
0x1800471d8  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x1800471dd  lea     rdx, [rcx-1]
0x1800471e1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800471e5  ja      short loc_1800471ED
0x1800471e7  call    cs:__imp_CloseHandle
0x1800471ed  mov     eax, edi
0x1800471ef  add     rsp, 68h
0x1800471f3  pop     r15
0x1800471f5  pop     r14
0x1800471f7  pop     rdi
0x1800471f8  pop     rsi
0x1800471f9  pop     rbp
0x1800471fa  pop     rbx
0x1800471fb  retn
0x1800471fc  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180047203  jz      short loc_1800471D8
0x180047205  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004720c  test    rax, rax
0x18004720f  jz      short loc_180047227
0x180047211  mov     r8d, edi
0x180047214  lea     rdx, aFailedToImpers; "Failed to Impersonate Client. Status = "...
0x18004721b  mov     ecx, 2
0x180047220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047225  jmp     short loc_1800471D8
0x180047227  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18004722f  jz      short loc_1800471D8
0x180047231  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180047239  jz      short loc_1800471D8
0x18004723b  mov     r8d, edi
0x18004723e  lea     rdx, aFailedToImpers; "Failed to Impersonate Client. Status = "...
0x180047245  mov     ecx, 2; unsigned int
0x18004724a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004724f  jmp     short loc_1800471D8
0x180047251  call    cs:__imp_GetLastError
0x180047257  mov     edi, eax
0x180047259  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180047260  jz      loc_180047135
0x180047266  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004726d  test    rax, rax
0x180047270  jz      short loc_18004728B
0x180047272  mov     r8d, edi
0x180047275  lea     rdx, aFailedToGetUse; "Failed to Get User's Token. Status = 0x"...
0x18004727c  mov     ecx, 2
0x180047281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047286  jmp     loc_180047135
0x18004728b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180047293  jz      loc_180047135
0x180047299  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800472a1  jz      loc_180047135
0x1800472a7  mov     r8d, edi
0x1800472aa  lea     rdx, aFailedToGetUse; "Failed to Get User's Token. Status = 0x"...
0x1800472b1  mov     ecx, 2; unsigned int
0x1800472b6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800472bb  jmp     loc_180047135
0x1800472c0  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800472c7  jz      loc_180047143
0x1800472cd  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800472d4  test    rax, rax
0x1800472d7  jz      short loc_1800472F2
0x1800472d9  mov     r8d, edi
0x1800472dc  lea     rdx, aRpcreverttosel; "RpcRevertToSelf Failed. Status = 0x%x"
0x1800472e3  mov     ecx, 2
0x1800472e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472ed  jmp     loc_180047143
0x1800472f2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800472fa  jz      loc_180047143
0x180047300  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180047308  jz      loc_180047143
0x18004730e  mov     r8d, edi
0x180047311  lea     rdx, aRpcreverttosel; "RpcRevertToSelf Failed. Status = 0x%x"
0x180047318  mov     ecx, 2; unsigned int
0x18004731d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180047322  jmp     loc_180047143
0x180047327  call    cs:__imp_GetLastError
0x18004732d  mov     edi, eax
0x18004732f  test    eax, eax
0x180047331  jz      loc_18004718C
0x180047337  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18004733e  jz      loc_1800471D8
0x180047344  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004734b  test    rax, rax
0x18004734e  jz      short loc_180047369
0x180047350  mov     r8d, edi
0x180047353  lea     rdx, aFailedToSessio; "Failed to session from token. Status = "...
0x18004735a  mov     ecx, 2
0x18004735f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047364  jmp     loc_1800471D8
0x180047369  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180047371  jz      loc_1800471D8
0x180047377  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004737f  jz      loc_1800471D8
0x180047385  mov     r8d, edi
0x180047388  lea     rdx, aFailedToSessio; "Failed to session from token. Status = "...
0x18004738f  mov     ecx, 2; unsigned int
0x180047394  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180047399  jmp     loc_1800471D8
```

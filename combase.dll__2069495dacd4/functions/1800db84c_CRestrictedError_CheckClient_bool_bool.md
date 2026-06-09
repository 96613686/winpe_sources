# CRestrictedError::CheckClient(bool,bool *)

- ea: `0x1800db84c`
- end: `0x1800dbb37`
- name: `?CheckClient@CRestrictedError@@AEAAJ_NPEA_N@Z`
- size: `747`
- prototype: `__int64 __fastcall(CRestrictedError *this, bool isRpc, bool *pfCanAccess)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800db760`

## callees

- `0x18003a8bc`
- `0x18003c7ec`
- `0x18003cf8c`
- `0x1800db84c`
- `0x1800dbb40`
- `0x1800dbbd8`
- `0x1800dbd70`
- `0x1800dc020`
- `0x1800dc2d0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800db8c4`
- `RPCRT4!RpcImpersonateClient` at `0x1800db8c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db8a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbb03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db8a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbb03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dbaed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dbb16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dbaed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dbb16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dba31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbacf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbaf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbb0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbb21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbb2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dba31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbacf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbaf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbb0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbb21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbb2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800db885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800db8ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800db9ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800db885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800db8ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800db9ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800db89b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800db902`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800db9c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800db89b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800db902`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800db9c3`

## string_xrefs

- `0x1800db9e4`: `onecore\com\combase\winrt\error\restrictederror.cpp`
- `0x1800dba10`: `onecore\com\combase\winrt\error\restrictederror.cpp`
- `0x1800dba44`: `onecore\com\combase\winrt\error\restrictederror.cpp`
- `0x1800dba91`: `onecore\com\combase\winrt\error\restrictederror.cpp`
- `0x1800dbab2`: `onecore\com\combase\winrt\error\restrictederror.cpp`

## pseudocode

```c
__int64 __fastcall CRestrictedError::CheckClient(CRestrictedError *this, bool isRpc, bool *pfCanAccess)
{
  HANDLE CurrentThread; // rax
  void *m_ptr; // rdi
  RPC_STATUS v6; // eax
  void *v7; // r14
  HANDLE v8; // rax
  CRestrictedError *v9; // rcx
  CRestrictedError *v10; // rcx
  int LastError; // ebx
  void *v13; // rdi
  HANDLE v14; // rax
  unsigned int v15; // edx
  void *v16; // rcx
  bool v17; // cc
  HRESULT v18; // eax
  DWORD v19; // ebx
  DWORD v20; // ebx
  void *retaddr; // [rsp+38h] [rbp+18h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > clientToken; // [rsp+40h] [rbp+20h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > token; // [rsp+50h] [rbp+30h] BYREF

  clientToken.m_ptr = 0;
  *pfCanAccess = 0;
  if ( isRpc )
  {
    token.m_ptr = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 4u, 1, &token.m_ptr) && GetLastError() != 1008 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    0x8C8u,
                    "onecore\\com\\combase\\winrt\\error\\restrictederror.cpp");
      if ( (unsigned __int64)token.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(token.m_ptr);
      goto LABEL_25;
    }
    m_ptr = token.m_ptr;
    token.m_ptr = 0;
    v6 = RpcImpersonateClient(0);
    if ( v6 )
    {
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              0x8CCu,
              "onecore\\com\\combase\\winrt\\error\\restrictederror.cpp",
              v6);
    }
    else
    {
      v7 = clientToken.m_ptr;
      if ( (unsigned __int64)clientToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v19 = GetLastError();
        CloseHandle(v7);
        SetLastError(v19);
      }
      clientToken.m_ptr = 0;
      v8 = GetCurrentThread();
      if ( OpenThreadToken(v8, 8u, 1, &clientToken.m_ptr) )
      {
        if ( m_ptr != (void *)-1LL )
          wil::details::RevertImpersonateToken(m_ptr);
        v9 = (CRestrictedError *)token.m_ptr;
        if ( (unsigned __int64)token.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(token.m_ptr);
LABEL_12:
        LastError = CRestrictedError::CheckClientPrivilege(v9, pfCanAccess, clientToken.m_ptr);
        if ( LastError < 0 )
        {
          v15 = 2256;
        }
        else
        {
          if ( *pfCanAccess
            || (LastError = CRestrictedError::CheckClientAccess(v10, pfCanAccess, clientToken.m_ptr), LastError >= 0) )
          {
            if ( (unsigned __int64)clientToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(clientToken.m_ptr);
            return 0;
          }
          v15 = 2259;
        }
        goto LABEL_24;
      }
      v18 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              0x8CDu,
              "onecore\\com\\combase\\winrt\\error\\restrictederror.cpp");
    }
    LastError = v18;
    if ( m_ptr != (void *)-1LL )
      wil::details::RevertImpersonateToken(m_ptr);
    if ( (unsigned __int64)token.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(token.m_ptr);
    v16 = clientToken.m_ptr;
    v17 = (unsigned __int64)clientToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
    goto LABEL_26;
  }
  LastError = CoImpersonateClient();
  if ( LastError >= 0 )
  {
    v13 = clientToken.m_ptr;
    if ( (unsigned __int64)clientToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v20 = GetLastError();
      CloseHandle(v13);
      SetLastError(v20);
    }
    clientToken.m_ptr = 0;
    v14 = GetCurrentThread();
    if ( !OpenThreadToken(v14, 8u, 1, &clientToken.m_ptr) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    0x8C1u,
                    "onecore\\com\\combase\\winrt\\error\\restrictederror.cpp");
      CoRevertToSelf();
      goto LABEL_25;
    }
    CoRevertToSelf();
    goto LABEL_12;
  }
  v15 = 2239;
LABEL_24:
  wil::details::in1diag3::Return_Hr(retaddr, v15, "onecore\\com\\combase\\winrt\\error\\restrictederror.cpp", LastError);
LABEL_25:
  v16 = clientToken.m_ptr;
  v17 = (unsigned __int64)clientToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_26:
  if ( v17 )
    CloseHandle(v16);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800db84c  mov     [rsp-18h+arg_8], rbx
0x1800db851  mov     [rsp-18h+arg_18], rsi
0x1800db856  mov     [rsp-18h+clientToken.m_ptr], rcx
0x1800db85b  push    rbp
0x1800db85c  push    rdi
0x1800db85d  push    r14
0x1800db85f  mov     rbp, rsp
0x1800db862  sub     rsp, 20h
0x1800db866  mov     [rbp+clientToken.m_ptr], 0
0x1800db86e  mov     rsi, pfCanAccess
0x1800db871  mov     byte ptr [pfCanAccess], 0
0x1800db875  test    isRpc, isRpc
0x1800db877  jz      loc_1800DB984
0x1800db87d  mov     [rbp+token.m_ptr], 0
0x1800db885  call    cs:__imp_GetCurrentThread
0x1800db88b  mov     edx, 4; DesiredAccess
0x1800db890  lea     r9, [rbp+token]; TokenHandle
0x1800db894  mov     rcx, rax; ThreadHandle
0x1800db897  lea     r8d, [rdx-3]; OpenAsSelf
0x1800db89b  call    cs:__imp_OpenThreadToken
0x1800db8a1  test    eax, eax
0x1800db8a3  jnz     short loc_1800DB8B6
0x1800db8a5  call    cs:__imp_GetLastError
0x1800db8ab  cmp     eax, 3F0h
0x1800db8b0  jnz     loc_1800DBA0C
0x1800db8b6  mov     rdi, [rbp+token.m_ptr]
0x1800db8ba  xor     ecx, ecx; BindingHandle
0x1800db8bc  mov     [rbp+token.m_ptr], 0
0x1800db8c4  call    cs:__imp_RpcImpersonateClient
0x1800db8ca  test    eax, eax
0x1800db8cc  jnz     loc_1800DBA40
0x1800db8d2  mov     r14, [rbp+clientToken.m_ptr]
0x1800db8d6  lea     rax, [r14-1]
0x1800db8da  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800db8de  jbe     loc_1800DBADA
0x1800db8e4  mov     [rbp+clientToken.m_ptr], 0
0x1800db8ec  call    cs:__imp_GetCurrentThread
0x1800db8f2  mov     edx, 8; DesiredAccess
0x1800db8f7  lea     r9, [rbp+clientToken]; TokenHandle
0x1800db8fb  mov     rcx, rax; ThreadHandle
0x1800db8fe  lea     r8d, [rdx-7]; OpenAsSelf
0x1800db902  call    cs:__imp_OpenThreadToken
0x1800db908  test    eax, eax
0x1800db90a  jz      loc_1800DBA8D
0x1800db910  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800db914  jz      short loc_1800DB91E
0x1800db916  mov     rcx, rdi; oldToken
0x1800db919  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800db91e  mov     rcx, [rbp+token.m_ptr]; hObject
0x1800db922  lea     rax, [rcx-1]
0x1800db926  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800db92a  jbe     loc_1800DBAF8
0x1800db930  mov     pfCanAccess, [rbp+clientToken.m_ptr]; hToken
0x1800db934  mov     rdx, rsi; pfCanAccess
0x1800db937  call    ?CheckClientPrivilege@CRestrictedError@@AEAAJPEA_NPEAX@Z; CRestrictedError::CheckClientPrivilege(bool *,void *)
0x1800db93c  mov     ebx, eax
0x1800db93e  test    eax, eax
0x1800db940  js      loc_1800DBA39
0x1800db946  cmp     byte ptr [rsi], 0
0x1800db949  jnz     short loc_1800DB95D
0x1800db94b  mov     pfCanAccess, [rbp+clientToken.m_ptr]; hToken
0x1800db94f  mov     rdx, rsi; pfCanAccess
0x1800db952  call    ?CheckClientAccess@CRestrictedError@@AEAAJPEA_NPEAX@Z; CRestrictedError::CheckClientAccess(bool *,void *)
0x1800db957  mov     ebx, eax
0x1800db959  test    eax, eax
0x1800db95b  js      short loc_1800DB9DB
0x1800db95d  mov     rcx, [rbp+clientToken.m_ptr]; hObject
0x1800db961  lea     rax, [rcx-1]
0x1800db965  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800db969  jbe     loc_1800DBACF
0x1800db96f  xor     eax, eax
0x1800db971  mov     rbx, [rsp+20h+arg_8]
0x1800db976  mov     rsi, [rsp+20h+arg_18]
0x1800db97b  add     rsp, 20h
0x1800db97f  pop     r14
0x1800db981  pop     rdi
0x1800db982  pop     rbp
0x1800db983  retn
0x1800db984  call    CoImpersonateClient
0x1800db989  mov     ebx, eax
0x1800db98b  test    eax, eax
0x1800db98d  js      loc_1800DBAA4
0x1800db993  mov     rdi, [rbp+clientToken.m_ptr]
0x1800db997  lea     rax, [rdi-1]
0x1800db99b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800db99f  jbe     loc_1800DBB03
0x1800db9a5  mov     [rbp+clientToken.m_ptr], 0
0x1800db9ad  call    cs:__imp_GetCurrentThread
0x1800db9b3  mov     edx, 8; DesiredAccess
0x1800db9b8  lea     r9, [rbp+clientToken]; TokenHandle
0x1800db9bc  mov     rcx, rax; ThreadHandle
0x1800db9bf  lea     r8d, [rdx-7]; OpenAsSelf
0x1800db9c3  call    cs:__imp_OpenThreadToken
0x1800db9c9  test    eax, eax
0x1800db9cb  jz      loc_1800DBAAE
0x1800db9d1  call    CoRevertToSelf
0x1800db9d6  jmp     loc_1800DB930
0x1800db9db  mov     edx, 8D3h; lineNumber
0x1800db9e0  mov     rcx, [rbp+18h]; callerReturnAddress
0x1800db9e4  lea     pfCanAccess, aOnecoreComComb_38; "onecore\\com\\combase\\winrt\\error\\re"...
0x1800db9eb  mov     r9d, ebx; hr
0x1800db9ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db9f3  mov     rcx, [rbp+clientToken.m_ptr]; hObject
0x1800db9f7  lea     rdx, [rcx-1]
0x1800db9fb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800db9ff  jbe     loc_1800DBB21
0x1800dba05  mov     eax, ebx
0x1800dba07  jmp     loc_1800DB971
0x1800dba0c  mov     rcx, [rbp+18h]; callerReturnAddress
0x1800dba10  lea     pfCanAccess, aOnecoreComComb_38; "onecore\\com\\combase\\winrt\\error\\re"...
0x1800dba17  mov     edx, 8C8h; lineNumber
0x1800dba1c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800dba21  mov     rcx, [rbp+token.m_ptr]; hObject
0x1800dba25  mov     ebx, eax
0x1800dba27  lea     rdx, [rcx-1]
0x1800dba2b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800dba2f  ja      short loc_1800DB9F3
0x1800dba31  call    cs:__imp_CloseHandle
0x1800dba37  jmp     short loc_1800DB9F3
0x1800dba39  mov     edx, 8D0h
0x1800dba3e  jmp     short loc_1800DB9E0
0x1800dba40  mov     rcx, [rbp+18h]; callerReturnAddress
0x1800dba44  lea     pfCanAccess, aOnecoreComComb_38; "onecore\\com\\combase\\winrt\\error\\re"...
0x1800dba4b  mov     r9d, eax; err
0x1800dba4e  mov     edx, 8CCh; lineNumber
0x1800dba53  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800dba58  mov     ebx, eax
0x1800dba5a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800dba5e  jnz     short loc_1800DBA83
0x1800dba60  mov     rcx, [rbp+token.m_ptr]; hObject
0x1800dba64  lea     rdx, [rcx-1]
0x1800dba68  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800dba6c  jbe     loc_1800DBB2C
0x1800dba72  mov     rcx, [rbp+clientToken.m_ptr]
0x1800dba76  lea     rax, [rcx-1]
0x1800dba7a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800dba7e  jmp     loc_1800DB9FF
0x1800dba83  mov     rcx, rdi; oldToken
0x1800dba86  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800dba8b  jmp     short loc_1800DBA60
0x1800dba8d  mov     rcx, [rbp+18h]; callerReturnAddress
0x1800dba91  lea     pfCanAccess, aOnecoreComComb_38; "onecore\\com\\combase\\winrt\\error\\re"...
0x1800dba98  mov     edx, 8CDh; lineNumber
0x1800dba9d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800dbaa2  jmp     short loc_1800DBA58
0x1800dbaa4  mov     edx, 8BFh
0x1800dbaa9  jmp     loc_1800DB9E0
0x1800dbaae  mov     rcx, [rbp+18h]; callerReturnAddress
0x1800dbab2  lea     pfCanAccess, aOnecoreComComb_38; "onecore\\com\\combase\\winrt\\error\\re"...
0x1800dbab9  mov     edx, 8C1h; lineNumber
0x1800dbabe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800dbac3  mov     ebx, eax
0x1800dbac5  call    CoRevertToSelf
0x1800dbaca  jmp     loc_1800DB9F3
0x1800dbacf  call    cs:__imp_CloseHandle
0x1800dbad5  jmp     loc_1800DB96F
0x1800dbada  call    cs:__imp_GetLastError
0x1800dbae0  mov     rcx, r14; hObject
0x1800dbae3  mov     ebx, eax
0x1800dbae5  call    cs:__imp_CloseHandle
0x1800dbaeb  mov     ecx, ebx; dwErrCode
0x1800dbaed  call    cs:__imp_SetLastError
0x1800dbaf3  jmp     loc_1800DB8E4
0x1800dbaf8  call    cs:__imp_CloseHandle
0x1800dbafe  jmp     loc_1800DB930
0x1800dbb03  call    cs:__imp_GetLastError
0x1800dbb09  mov     rcx, rdi; hObject
0x1800dbb0c  mov     ebx, eax
0x1800dbb0e  call    cs:__imp_CloseHandle
0x1800dbb14  mov     ecx, ebx; dwErrCode
0x1800dbb16  call    cs:__imp_SetLastError
0x1800dbb1c  jmp     loc_1800DB9A5
0x1800dbb21  call    cs:__imp_CloseHandle
0x1800dbb27  jmp     loc_1800DBA05
0x1800dbb2c  call    cs:__imp_CloseHandle
0x1800dbb32  jmp     loc_1800DBA72
```

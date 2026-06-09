# CheckCallerPrivilege(void)

- ea: `0x1800231b8`
- end: `0x1800232bb`
- name: `?CheckCallerPrivilege@@YAKXZ`
- size: `259`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023730`

## callees

- `0x1800231b8`
- `0x1800232c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023216`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023203`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002328a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023298`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002328a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023298`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180023263`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180023263`
- `RPCRT4!RpcImpersonateClient` at `0x1800231eb`
- `RPCRT4!RpcImpersonateClient` at `0x1800231eb`
- `RPCRT4!RpcRevertToSelf` at `0x180023228`
- `RPCRT4!RpcRevertToSelf` at `0x1800232a3`
- `RPCRT4!RpcRevertToSelf` at `0x180023228`
- `RPCRT4!RpcRevertToSelf` at `0x1800232a3`

## pseudocode

```c
__int64 CheckCallerPrivilege(void)
{
  PSID *v0; // r14
  HANDLE v1; // rdi
  unsigned int v2; // ebx
  int v3; // esi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v6; // eax
  void *v7; // rcx
  unsigned int v8; // eax
  int v10; // [rsp+50h] [rbp+30h] BYREF
  WINBOOL IsMember; // [rsp+58h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+40h] BYREF
  HANDLE v13; // [rsp+68h] [rbp+48h] BYREF

  v0 = (PSID *)qword_180031828;
  v1 = 0;
  v13 = 0;
  TokenHandle = 0;
  IsMember = 0;
  v10 = 0;
  v2 = RpcImpersonateClient(0);
  if ( v2 )
  {
    v3 = 0;
    goto LABEL_14;
  }
  v3 = 1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
LABEL_13:
    v2 = LastError;
    goto LABEL_14;
  }
  v2 = RpcRevertToSelf();
  if ( !v2 )
  {
    v3 = 0;
    v6 = CheckForLowIntegrityAndGenerateMediumIntegrityToken(TokenHandle, &v13, &v10);
    v1 = v13;
    v2 = v6;
    if ( !v6 )
    {
      v7 = TokenHandle;
      if ( v10 )
        v7 = v13;
      if ( !CheckTokenMembership(v7, *v0, &IsMember) )
      {
        v2 = 5;
        goto LABEL_14;
      }
      LastError = 0;
      if ( !IsMember )
        LastError = 5;
      goto LABEL_13;
    }
  }
LABEL_14:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v1 )
    CloseHandle(v1);
  if ( v3 == 1 )
  {
    v8 = RpcRevertToSelf();
    if ( v8 )
      return v8;
  }
  return v2;
}

```

## disassembly

```asm
0x1800231b8  push    rbp
0x1800231ba  push    rbx
0x1800231bb  push    rsi
0x1800231bc  push    rdi
0x1800231bd  push    r14
0x1800231bf  mov     rbp, rsp
0x1800231c2  sub     rsp, 20h
0x1800231c6  mov     r14, cs:qword_180031828
0x1800231cd  xor     edi, edi
0x1800231cf  xor     ecx, ecx; BindingHandle
0x1800231d1  mov     [rbp+arg_18], rdi
0x1800231d5  mov     [rbp+TokenHandle], 0
0x1800231dd  mov     [rbp+IsMember], 0
0x1800231e4  mov     [rbp+arg_0], 0
0x1800231eb  call    cs:__imp_RpcImpersonateClient
0x1800231f1  mov     ebx, eax
0x1800231f3  test    eax, eax
0x1800231f5  jz      short loc_1800231FE
0x1800231f7  xor     esi, esi
0x1800231f9  jmp     loc_180023281
0x1800231fe  mov     esi, 1
0x180023203  call    cs:__imp_GetCurrentThread
0x180023209  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002320d  mov     r8d, esi; OpenAsSelf
0x180023210  mov     rcx, rax; ThreadHandle
0x180023213  lea     edx, [rsi+0Dh]; DesiredAccess
0x180023216  call    cs:__imp_OpenThreadToken
0x18002321c  test    eax, eax
0x18002321e  jnz     short loc_180023228
0x180023220  call    cs:__imp_GetLastError
0x180023226  jmp     short loc_18002327F
0x180023228  call    cs:__imp_RpcRevertToSelf
0x18002322e  mov     ebx, eax
0x180023230  test    eax, eax
0x180023232  jnz     short loc_180023281
0x180023234  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180023238  lea     r8, [rbp+arg_0]; int *
0x18002323c  lea     rdx, [rbp+arg_18]; void **
0x180023240  xor     esi, esi
0x180023242  call    ?CheckForLowIntegrityAndGenerateMediumIntegrityToken@@YAKPEAXPEAPEAXPEAH@Z; CheckForLowIntegrityAndGenerateMediumIntegrityToken(void *,void * *,int *)
0x180023247  mov     rdi, [rbp+arg_18]
0x18002324b  mov     ebx, eax
0x18002324d  test    eax, eax
0x18002324f  jnz     short loc_180023281
0x180023251  mov     rcx, [rbp+TokenHandle]
0x180023255  lea     r8, [rbp+IsMember]; IsMember
0x180023259  cmp     [rbp+arg_0], esi
0x18002325c  mov     rdx, [r14]; SidToCheck
0x18002325f  cmovnz  rcx, rdi; TokenHandle
0x180023263  call    cs:__imp_CheckTokenMembership
0x180023269  test    eax, eax
0x18002326b  jnz     short loc_180023272
0x18002326d  lea     ebx, [rsi+5]
0x180023270  jmp     short loc_180023281
0x180023272  cmp     [rbp+IsMember], esi
0x180023275  mov     eax, ebx
0x180023277  mov     ebx, 5
0x18002327c  cmovz   eax, ebx
0x18002327f  mov     ebx, eax
0x180023281  mov     rcx, [rbp+TokenHandle]; hObject
0x180023285  test    rcx, rcx
0x180023288  jz      short loc_180023290
0x18002328a  call    cs:__imp_CloseHandle
0x180023290  test    rdi, rdi
0x180023293  jz      short loc_18002329E
0x180023295  mov     rcx, rdi; hObject
0x180023298  call    cs:__imp_CloseHandle
0x18002329e  cmp     esi, 1
0x1800232a1  jnz     short loc_1800232AE
0x1800232a3  call    cs:__imp_RpcRevertToSelf
0x1800232a9  test    eax, eax
0x1800232ab  cmovnz  ebx, eax
0x1800232ae  mov     eax, ebx
0x1800232b0  add     rsp, 20h
0x1800232b4  pop     r14
0x1800232b6  pop     rdi
0x1800232b7  pop     rsi
0x1800232b8  pop     rbx
0x1800232b9  pop     rbp
0x1800232ba  retn
```

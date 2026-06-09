# NetpAccessCheck2

- ea: `0x180003700`
- end: `0x180003869`
- name: `NetpAccessCheck2`
- size: `361`
- prototype: `RPC_STATUS __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD DesiredAccess, __int64, int)`
- caller_count: `19`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029680`
- `0x18002b110`
- `0x18002b400`
- `0x180032f10`
- `0x180032ff0`
- `0x18003fea0`
- `0x18005a680`
- `0x18005a840`
- `0x18005abe0`
- `0x18005af40`
- `0x18005b270`
- `0x18005b500`
- `0x18005b7e0`
- `0x18005d040`
- `0x18005d1c0`
- `0x18005d3e0`
- `0x18005d440`
- `0x18005ee20`
- `0x18005f0a0`

## callees

- `0x180003700`
- `0x18000e270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003822`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000376d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000376d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003754`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003754`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000383e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000383e`
- `RPCRT4!RpcImpersonateClient` at `0x180003746`
- `RPCRT4!RpcImpersonateClient` at `0x180003746`
- `RPCRT4!RpcRevertToSelf` at `0x18000382e`
- `RPCRT4!RpcRevertToSelf` at `0x18000382e`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003808`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003808`
- `ntdll!NtQueryInformationToken` at `0x1800037af`
- `ntdll!NtQueryInformationToken` at `0x1800037af`

## pseudocode

```c
RPC_STATUS __fastcall NetpAccessCheck2(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        DWORD DesiredAccess,
        __int64 a3,
        int a4)
{
  RPC_STATUS result; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  int TokenInformation; // [rsp+40h] [rbp-248h] BYREF
  ULONG ReturnLength; // [rsp+44h] [rbp-244h] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-240h] BYREF
  WINBOOL AccessStatus; // [rsp+4Ch] [rbp-23Ch] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-238h] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-230h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-228h] BYREF

  TokenHandle = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  result = RpcImpersonateClient(0);
  if ( !result )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      if ( a4
        || (TokenInformation = 0,
            ReturnLength = 0,
            NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) >= 0)
        && !TokenInformation )
      {
        PrivilegeSetLength = 500;
        if ( AccessCheck(
               pSecurityDescriptor,
               TokenHandle,
               DesiredAccess,
               &NlGlobalNetlogonInfoMapping,
               &PrivilegeSet,
               &PrivilegeSetLength,
               &GrantedAccess,
               &AccessStatus)
          && AccessStatus )
        {
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
        }
      }
      else
      {
        LastError = 5;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    RpcRevertToSelf();
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180003700  mov     [rsp+arg_10], rbx
0x180003705  push    rbp
0x180003706  push    rsi
0x180003707  push    rdi
0x180003708  sub     rsp, 270h
0x18000370f  mov     rax, cs:__security_cookie
0x180003716  xor     rax, rsp
0x180003719  mov     [rsp+288h+var_28], rax
0x180003721  xor     ebp, ebp
0x180003723  mov     rdi, rcx
0x180003726  xor     ecx, ecx; BindingHandle
0x180003728  mov     [rsp+288h+TokenHandle], rbp
0x18000372d  mov     [rsp+288h+var_230], ebp
0x180003731  mov     ebx, r9d
0x180003734  mov     [rsp+288h+var_23C], ebp
0x180003738  mov     esi, edx
0x18000373a  mov     [rsp+288h+var_240], ebp
0x18000373e  mov     [rsp+288h+TokenInformation], ebp
0x180003742  mov     [rsp+288h+var_244], ebp
0x180003746  call    cs:__imp_RpcImpersonateClient
0x18000374c  test    eax, eax
0x18000374e  jnz     loc_180003846
0x180003754  call    cs:__imp_GetCurrentThread
0x18000375a  lea     r9, [rsp+288h+TokenHandle]; TokenHandle
0x18000375f  mov     edx, 8; DesiredAccess
0x180003764  mov     rcx, rax; ThreadHandle
0x180003767  mov     r8d, 1; OpenAsSelf
0x18000376d  call    cs:__imp_OpenThreadToken
0x180003773  test    eax, eax
0x180003775  jnz     short loc_180003784
0x180003777  call    cs:__imp_GetLastError
0x18000377d  mov     ebx, eax
0x18000377f  jmp     loc_18000382E
0x180003784  test    ebx, ebx
0x180003786  jnz     short loc_1800037C6
0x180003788  mov     rcx, [rsp+288h+TokenHandle]; TokenHandle
0x18000378d  lea     rax, [rsp+288h+var_244]
0x180003792  mov     r9d, 4; TokenInformationLength
0x180003798  mov     [rsp+288h+ReturnLength], rax; ReturnLength
0x18000379d  lea     r8, [rsp+288h+TokenInformation]; TokenInformation
0x1800037a2  mov     [rsp+288h+TokenInformation], ebp
0x1800037a6  mov     edx, 1Dh; TokenInformationClass
0x1800037ab  mov     [rsp+288h+var_244], ebp
0x1800037af  call    cs:__imp_NtQueryInformationToken
0x1800037b5  test    eax, eax
0x1800037b7  js      short loc_1800037BF
0x1800037b9  cmp     [rsp+288h+TokenInformation], ebp
0x1800037bd  jz      short loc_1800037C6
0x1800037bf  mov     ebx, 5
0x1800037c4  jmp     short loc_18000382E
0x1800037c6  mov     rdx, [rsp+288h+TokenHandle]; ClientToken
0x1800037cb  lea     rax, [rsp+288h+var_23C]
0x1800037d0  mov     [rsp+288h+AccessStatus], rax; AccessStatus
0x1800037d5  lea     r9, ?NlGlobalNetlogonInfoMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x1800037dc  lea     rax, [rsp+288h+var_230]
0x1800037e1  mov     [rsp+288h+var_240], 1F4h
0x1800037e9  mov     [rsp+288h+GrantedAccess], rax; GrantedAccess
0x1800037ee  mov     r8d, esi; DesiredAccess
0x1800037f1  lea     rax, [rsp+288h+var_240]
0x1800037f6  mov     rcx, rdi; pSecurityDescriptor
0x1800037f9  mov     [rsp+288h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800037fe  lea     rax, [rsp+288h+PrivilegeSet]
0x180003803  mov     [rsp+288h+ReturnLength], rax; PrivilegeSet
0x180003808  call    cs:__imp_AccessCheck
0x18000380e  test    eax, eax
0x180003810  jnz     short loc_18000381C
0x180003812  call    cs:__imp_GetLastError
0x180003818  mov     ebx, eax
0x18000381a  jmp     short loc_18000382E
0x18000381c  cmp     [rsp+288h+var_23C], ebp
0x180003820  jnz     short loc_18000382C
0x180003822  call    cs:__imp_GetLastError
0x180003828  mov     ebx, eax
0x18000382a  jmp     short loc_18000382E
0x18000382c  mov     ebx, ebp
0x18000382e  call    cs:__imp_RpcRevertToSelf
0x180003834  mov     rcx, [rsp+288h+TokenHandle]; hObject
0x180003839  test    rcx, rcx
0x18000383c  jz      short loc_180003844
0x18000383e  call    cs:__imp_CloseHandle
0x180003844  mov     eax, ebx
0x180003846  mov     rcx, [rsp+288h+var_28]
0x18000384e  xor     rcx, rsp; StackCookie
0x180003851  call    __security_check_cookie
0x180003856  mov     rbx, [rsp+288h+arg_10]
0x18000385e  add     rsp, 270h
0x180003865  pop     rdi
0x180003866  pop     rsi
0x180003867  pop     rbp
0x180003868  retn
```

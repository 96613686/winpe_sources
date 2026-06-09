# NetpAccessCheck2

- ea: `0x180003890`
- end: `0x180003a36`
- name: `NetpAccessCheck2`
- size: `422`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD DesiredAccess)`
- caller_count: `19`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ada0`
- `0x18002ca10`
- `0x18002cd20`
- `0x180034dc0`
- `0x180034ea0`
- `0x180042880`
- `0x18005e870`
- `0x18005ea30`
- `0x18005ee10`
- `0x18005f180`
- `0x18005f4c0`
- `0x18005f750`
- `0x18005fa30`
- `0x1800613f0`
- `0x180061580`
- `0x1800617a0`
- `0x180061800`
- `0x180063280`
- `0x180063510`

## callees

- `0x180003890`
- `0x18000e910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003909`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003909`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800038ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800038ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a04`
- `RPCRT4!RpcImpersonateClient` at `0x1800038d6`
- `RPCRT4!RpcImpersonateClient` at `0x1800038d6`
- `RPCRT4!RpcRevertToSelf` at `0x1800039ee`
- `RPCRT4!RpcRevertToSelf` at `0x1800039ee`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800039b6`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800039b6`
- `ntdll!NtQueryInformationToken` at `0x180003957`
- `ntdll!NtQueryInformationToken` at `0x180003957`

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
0x180003890  mov     [rsp+arg_10], rbx
0x180003895  push    rbp
0x180003896  push    rsi
0x180003897  push    rdi
0x180003898  sub     rsp, 270h
0x18000389f  mov     rax, cs:__security_cookie
0x1800038a6  xor     rax, rsp
0x1800038a9  mov     [rsp+288h+var_28], rax
0x1800038b1  xor     ebp, ebp
0x1800038b3  mov     rdi, rcx
0x1800038b6  xor     ecx, ecx; BindingHandle
0x1800038b8  mov     [rsp+288h+TokenHandle], rbp
0x1800038bd  mov     [rsp+288h+var_230], ebp
0x1800038c1  mov     ebx, r9d
0x1800038c4  mov     [rsp+288h+var_23C], ebp
0x1800038c8  mov     esi, edx
0x1800038ca  mov     [rsp+288h+var_240], ebp
0x1800038ce  mov     [rsp+288h+TokenInformation], ebp
0x1800038d2  mov     [rsp+288h+var_244], ebp
0x1800038d6  call    cs:__imp_RpcImpersonateClient
0x1800038dd  nop     dword ptr [rax+rax+00h]
0x1800038e2  test    eax, eax
0x1800038e4  jnz     loc_180003A12
0x1800038ea  call    cs:__imp_GetCurrentThread
0x1800038f1  nop     dword ptr [rax+rax+00h]
0x1800038f6  lea     r9, [rsp+288h+TokenHandle]; TokenHandle
0x1800038fb  mov     edx, 8; DesiredAccess
0x180003900  mov     rcx, rax; ThreadHandle
0x180003903  mov     r8d, 1; OpenAsSelf
0x180003909  call    cs:__imp_OpenThreadToken
0x180003910  nop     dword ptr [rax+rax+00h]
0x180003915  test    eax, eax
0x180003917  jnz     short loc_18000392C
0x180003919  call    cs:__imp_GetLastError
0x180003920  nop     dword ptr [rax+rax+00h]
0x180003925  mov     ebx, eax
0x180003927  jmp     loc_1800039EE
0x18000392c  test    ebx, ebx
0x18000392e  jnz     short loc_180003974
0x180003930  mov     rcx, [rsp+288h+TokenHandle]; TokenHandle
0x180003935  lea     rax, [rsp+288h+var_244]
0x18000393a  mov     r9d, 4; TokenInformationLength
0x180003940  mov     [rsp+288h+ReturnLength], rax; ReturnLength
0x180003945  lea     r8, [rsp+288h+TokenInformation]; TokenInformation
0x18000394a  mov     [rsp+288h+TokenInformation], ebp
0x18000394e  mov     edx, 1Dh; TokenInformationClass
0x180003953  mov     [rsp+288h+var_244], ebp
0x180003957  call    cs:__imp_NtQueryInformationToken
0x18000395e  nop     dword ptr [rax+rax+00h]
0x180003963  test    eax, eax
0x180003965  js      short loc_18000396D
0x180003967  cmp     [rsp+288h+TokenInformation], ebp
0x18000396b  jz      short loc_180003974
0x18000396d  mov     ebx, 5
0x180003972  jmp     short loc_1800039EE
0x180003974  mov     rdx, [rsp+288h+TokenHandle]; ClientToken
0x180003979  lea     rax, [rsp+288h+var_23C]
0x18000397e  mov     [rsp+288h+AccessStatus], rax; AccessStatus
0x180003983  lea     r9, ?NlGlobalNetlogonInfoMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18000398a  lea     rax, [rsp+288h+var_230]
0x18000398f  mov     [rsp+288h+var_240], 1F4h
0x180003997  mov     [rsp+288h+GrantedAccess], rax; GrantedAccess
0x18000399c  mov     r8d, esi; DesiredAccess
0x18000399f  lea     rax, [rsp+288h+var_240]
0x1800039a4  mov     rcx, rdi; pSecurityDescriptor
0x1800039a7  mov     [rsp+288h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800039ac  lea     rax, [rsp+288h+PrivilegeSet]
0x1800039b1  mov     [rsp+288h+ReturnLength], rax; PrivilegeSet
0x1800039b6  call    cs:__imp_AccessCheck
0x1800039bd  nop     dword ptr [rax+rax+00h]
0x1800039c2  test    eax, eax
0x1800039c4  jnz     short loc_1800039D6
0x1800039c6  call    cs:__imp_GetLastError
0x1800039cd  nop     dword ptr [rax+rax+00h]
0x1800039d2  mov     ebx, eax
0x1800039d4  jmp     short loc_1800039EE
0x1800039d6  cmp     [rsp+288h+var_23C], ebp
0x1800039da  jnz     short loc_1800039EC
0x1800039dc  call    cs:__imp_GetLastError
0x1800039e3  nop     dword ptr [rax+rax+00h]
0x1800039e8  mov     ebx, eax
0x1800039ea  jmp     short loc_1800039EE
0x1800039ec  mov     ebx, ebp
0x1800039ee  call    cs:__imp_RpcRevertToSelf
0x1800039f5  nop     dword ptr [rax+rax+00h]
0x1800039fa  mov     rcx, [rsp+288h+TokenHandle]; hObject
0x1800039ff  test    rcx, rcx
0x180003a02  jz      short loc_180003A10
0x180003a04  call    cs:__imp_CloseHandle
0x180003a0b  nop     dword ptr [rax+rax+00h]
0x180003a10  mov     eax, ebx
0x180003a12  mov     rcx, [rsp+288h+var_28]
0x180003a1a  xor     rcx, rsp; StackCookie
0x180003a1d  call    __security_check_cookie
0x180003a22  mov     rbx, [rsp+288h+arg_10]
0x180003a2a  add     rsp, 270h
0x180003a31  pop     rdi
0x180003a32  pop     rsi
0x180003a33  pop     rbp
0x180003a34  retn
```

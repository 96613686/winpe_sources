# _CatDBCanWriteToPathWithImpersonation(void *,ushort const *)

- ea: `0x18001cf60`
- end: `0x18001d17c`
- name: `?_CatDBCanWriteToPathWithImpersonation@@YAKPEAXPEBG@Z`
- size: `540`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, LPCWSTR lpFileName)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017a04`
- `0x180019314`
- `0x18001caa0`
- `0x18001cb50`
- `0x18001cca0`

## callees

- `0x1800015b0`
- `0x180003538`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000be40`
- `0x18001cf60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d054`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d11e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d054`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d11e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d079`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d079`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d065`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d065`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d143`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d143`
- `RPCRT4!RpcRevertToSelf` at `0x18001d110`
- `RPCRT4!RpcRevertToSelf` at `0x18001d110`
- `RPCRT4!RpcImpersonateClient` at `0x18001d048`
- `RPCRT4!RpcImpersonateClient` at `0x18001d048`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001cfdb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001d02f`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001cfdb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001d02f`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18001d0b3`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18001d0b3`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001d0ec`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001d0ec`

## pseudocode

```c
__int64 __fastcall _CatDBCanWriteToPathWithImpersonation(RPC_BINDING_HANDLE BindingHandle, LPCWSTR lpFileName)
{
  void *v4; // rdi
  unsigned int Error; // ebx
  RPC_STATUS v6; // eax
  unsigned int v7; // edx
  unsigned __int16 *v8; // rcx
  unsigned int v9; // r8d
  HANDLE CurrentThread; // rax
  RPC_STATUS v11; // eax
  int PrivilegeSetLength; // [rsp+28h] [rbp-21h]
  DWORD nLengthNeeded; // [rsp+40h] [rbp-9h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-1h] BYREF
  DWORD AccessMask; // [rsp+50h] [rbp+7h] BYREF
  WINBOOL AccessStatus; // [rsp+54h] [rbp+Bh] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp+Fh] BYREF
  DWORD v19; // [rsp+5Ch] [rbp+13h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+17h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+27h] BYREF

  AccessStatus = 0;
  nLengthNeeded = 0;
  TokenHandle = 0;
  AccessMask = 2;
  GrantedAccess = 0;
  v4 = 0;
  v19 = 20;
  GenericMapping = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  if ( GetFileSecurityW(lpFileName, 0x17u, 0, 0, &nLengthNeeded) )
  {
    Error = 1287;
    goto LABEL_20;
  }
  Error = _CatDBGetNonzeroLastError();
  if ( Error == 122 )
  {
    v4 = _CatDBAlloc(nLengthNeeded);
    if ( !v4 )
    {
      Error = 14;
      goto LABEL_20;
    }
    if ( !GetFileSecurityW(lpFileName, 0x17u, v4, nLengthNeeded, &nLengthNeeded) )
    {
      Error = _CatDBGetNonzeroLastError();
      goto LABEL_20;
    }
    v6 = RpcImpersonateClient(BindingHandle);
    if ( v6 )
    {
      SetLastError(v6);
      v9 = 1861;
LABEL_19:
      ErrLog_LogError(v8, v7, v9, 0, 0, PrivilegeSetLength);
      goto LABEL_20;
    }
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle)
      && (GenericMapping.GenericRead = 1179785,
          GenericMapping.GenericWrite = 1179926,
          GenericMapping.GenericExecute = 1179808,
          GenericMapping.GenericAll = 2032127,
          MapGenericMask(&AccessMask, &GenericMapping),
          AccessCheck(v4, TokenHandle, AccessMask, &GenericMapping, &PrivilegeSet, &v19, &GrantedAccess, &AccessStatus)) )
    {
      if ( AccessStatus && (AccessMask & GrantedAccess) == AccessMask )
        Error = 0;
      else
        Error = 5;
    }
    else
    {
      Error = _CatDBGetNonzeroLastError();
    }
    v11 = RpcRevertToSelf();
    if ( v11 )
    {
      Error = v11;
      SetLastError(v11);
      v9 = 1910;
      goto LABEL_19;
    }
  }
LABEL_20:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 )
    _CatDBFree(v4);
  return Error;
}

```

## disassembly

```asm
0x18001cf60  mov     [rsp-8+arg_10], rbx
0x18001cf65  mov     [rsp-8+arg_18], rsi
0x18001cf6a  push    rbp
0x18001cf6b  push    rdi
0x18001cf6c  push    r14
0x18001cf6e  lea     rbp, [rsp-47h]
0x18001cf73  sub     rsp, 90h
0x18001cf7a  mov     rax, cs:__security_cookie
0x18001cf81  xor     rax, rsp
0x18001cf84  mov     [rbp+57h+var_18], rax
0x18001cf88  xor     eax, eax
0x18001cf8a  mov     [rbp+57h+var_4C], 0
0x18001cf91  mov     r14, rdx
0x18001cf94  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x18001cf97  mov     [rbp+57h+nLengthNeeded], eax
0x18001cf9a  mov     rsi, rcx
0x18001cf9d  mov     [rbp+57h+TokenHandle], rax
0x18001cfa1  xorps   xmm0, xmm0
0x18001cfa4  xorps   xmm1, xmm1
0x18001cfa7  mov     [rbp+57h+AccessMask], 2
0x18001cfae  lea     rax, [rbp+57h+nLengthNeeded]
0x18001cfb2  mov     [rbp+57h+var_48], 0
0x18001cfb9  xor     edi, edi
0x18001cfbb  mov     [rbp+57h+var_44], 14h
0x18001cfc2  xor     r9d, r9d; nLength
0x18001cfc5  mov     [rsp+0A0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001cfca  xor     r8d, r8d; pSecurityDescriptor
0x18001cfcd  mov     rcx, r14; lpFileName
0x18001cfd0  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18001cfd4  lea     edx, [rdi+17h]; RequestedInformation
0x18001cfd7  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm1
0x18001cfdb  call    cs:__imp_GetFileSecurityW
0x18001cfe1  test    eax, eax
0x18001cfe3  jz      short loc_18001CFEF
0x18001cfe5  mov     ebx, 507h
0x18001cfea  jmp     loc_18001D13A
0x18001cfef  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001cff4  mov     ebx, eax
0x18001cff6  cmp     eax, 7Ah ; 'z'
0x18001cff9  jnz     loc_18001D13A
0x18001cfff  mov     ecx, [rbp+57h+nLengthNeeded]; uBytes
0x18001d002  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x18001d007  mov     rdi, rax
0x18001d00a  test    rax, rax
0x18001d00d  jnz     short loc_18001D017
0x18001d00f  lea     ebx, [rax+0Eh]
0x18001d012  jmp     loc_18001D13A
0x18001d017  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x18001d01b  lea     rax, [rbp+57h+nLengthNeeded]
0x18001d01f  mov     r8, rdi; pSecurityDescriptor
0x18001d022  mov     [rsp+0A0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001d027  mov     edx, 17h; RequestedInformation
0x18001d02c  mov     rcx, r14; lpFileName
0x18001d02f  call    cs:__imp_GetFileSecurityW
0x18001d035  test    eax, eax
0x18001d037  jnz     short loc_18001D045
0x18001d039  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001d03e  mov     ebx, eax
0x18001d040  jmp     loc_18001D13A
0x18001d045  mov     rcx, rsi; BindingHandle
0x18001d048  call    cs:__imp_RpcImpersonateClient
0x18001d04e  test    eax, eax
0x18001d050  jz      short loc_18001D065
0x18001d052  mov     ecx, eax; dwErrCode
0x18001d054  call    cs:__imp_SetLastError
0x18001d05a  mov     r8d, 745h
0x18001d060  jmp     loc_18001D12A
0x18001d065  call    cs:__imp_GetCurrentThread
0x18001d06b  xor     r8d, r8d; OpenAsSelf
0x18001d06e  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001d072  mov     rcx, rax; ThreadHandle
0x18001d075  lea     edx, [r8+8]; DesiredAccess
0x18001d079  call    cs:__imp_OpenThreadToken
0x18001d07f  test    eax, eax
0x18001d081  jnz     short loc_18001D08F
0x18001d083  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001d088  mov     ebx, eax
0x18001d08a  jmp     loc_18001D110
0x18001d08f  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18001d093  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x18001d09a  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18001d09e  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x18001d0a5  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x18001d0ac  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x18001d0b3  call    cs:__imp_MapGenericMask
0x18001d0b9  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18001d0bd  lea     rax, [rbp+57h+var_4C]
0x18001d0c1  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18001d0c5  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18001d0c9  mov     [rsp+0A0h+AccessStatus], rax; AccessStatus
0x18001d0ce  mov     rcx, rdi; pSecurityDescriptor
0x18001d0d1  lea     rax, [rbp+57h+var_48]
0x18001d0d5  mov     [rsp+0A0h+GrantedAccess], rax; GrantedAccess
0x18001d0da  lea     rax, [rbp+57h+var_44]
0x18001d0de  mov     [rsp+0A0h+PrivilegeSetLength], rax; int
0x18001d0e3  lea     rax, [rbp+57h+PrivilegeSet]
0x18001d0e7  mov     [rsp+0A0h+lpnLengthNeeded], rax; PrivilegeSet
0x18001d0ec  call    cs:__imp_AccessCheck
0x18001d0f2  test    eax, eax
0x18001d0f4  jz      short loc_18001D083
0x18001d0f6  cmp     [rbp+57h+var_4C], 0
0x18001d0fa  jz      short loc_18001D10B
0x18001d0fc  mov     eax, [rbp+57h+var_48]
0x18001d0ff  and     eax, [rbp+57h+AccessMask]
0x18001d102  cmp     eax, [rbp+57h+AccessMask]
0x18001d105  jnz     short loc_18001D10B
0x18001d107  xor     ebx, ebx
0x18001d109  jmp     short loc_18001D110
0x18001d10b  mov     ebx, 5
0x18001d110  call    cs:__imp_RpcRevertToSelf
0x18001d116  test    eax, eax
0x18001d118  jz      short loc_18001D13A
0x18001d11a  mov     ecx, eax; dwErrCode
0x18001d11c  mov     ebx, eax
0x18001d11e  call    cs:__imp_SetLastError
0x18001d124  mov     r8d, 776h; unsigned int
0x18001d12a  xor     r9d, r9d; unsigned int
0x18001d12d  mov     dword ptr [rsp+0A0h+lpnLengthNeeded], 0; int
0x18001d135  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001d13a  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001d13e  test    rcx, rcx
0x18001d141  jz      short loc_18001D149
0x18001d143  call    cs:__imp_CloseHandle
0x18001d149  test    rdi, rdi
0x18001d14c  jz      short loc_18001D156
0x18001d14e  mov     rcx, rdi; void *
0x18001d151  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d156  mov     eax, ebx
0x18001d158  mov     rcx, [rbp+57h+var_18]
0x18001d15c  xor     rcx, rsp; StackCookie
0x18001d15f  call    __security_check_cookie
0x18001d164  lea     r11, [rsp+0A0h+var_10]
0x18001d16c  mov     rbx, [r11+30h]
0x18001d170  mov     rsi, [r11+38h]
0x18001d174  mov     rsp, r11
0x18001d177  pop     r14
0x18001d179  pop     rdi
0x18001d17a  pop     rbp
0x18001d17b  retn
```

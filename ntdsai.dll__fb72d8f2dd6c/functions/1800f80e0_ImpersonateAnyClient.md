# ImpersonateAnyClient

- ea: `0x1800f80e0`
- end: `0x1800f8251`
- name: `ImpersonateAnyClient`
- size: `369`
- prototype: `__int64(void)`
- caller_count: `20`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b3e8`
- `0x18004b918`
- `0x1800f8260`
- `0x18011ccd8`
- `0x18011f734`
- `0x180121330`
- `0x1801260a4`
- `0x180133114`
- `0x1801340f8`
- `0x1801362b0`
- `0x180136c90`
- `0x180137e3c`
- `0x1801397cc`
- `0x1801822d0`
- `0x18023c5e8`
- `0x1802984f4`
- `0x1802aecc8`
- `0x18030fce4`
- `0x18037ddd4`
- `0x1803ae74c`

## callees

- `0x1800f80e0`
- `0x180126014`
- `0x180172ffc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f80ec`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f81a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f80ec`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f81a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f821c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f821c`
- `RPCRT4!RpcImpersonateClient` at `0x1800f80fa`
- `RPCRT4!RpcImpersonateClient` at `0x1800f81d1`
- `RPCRT4!RpcImpersonateClient` at `0x1800f80fa`
- `RPCRT4!RpcImpersonateClient` at `0x1800f81d1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800f8161`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800f8161`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x1800f8225`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x1800f8225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8170`
- `SspiCli!ImpersonateSecurityContext` at `0x1800f8187`
- `SspiCli!ImpersonateSecurityContext` at `0x1800f81b6`
- `SspiCli!ImpersonateSecurityContext` at `0x1800f8187`
- `SspiCli!ImpersonateSecurityContext` at `0x1800f81b6`
- `SAMSRV!SamIImpersonateNullSession` at `0x1800f8210`
- `SAMSRV!SamIImpersonateNullSession` at `0x1800f8210`

## pseudocode

```c
RPC_STATUS ImpersonateAnyClient()
{
  char *Value; // rax
  char *v1; // rcx
  RPC_STATUS result; // eax
  _DWORD *v3; // rdi
  struct _SecHandle *v4; // rax
  void *v5; // rax
  PCtxtHandle *v6; // rax
  HANDLE CurrentThread; // rax

  Value = (char *)TlsGetValue(dwTSindex);
  v1 = Value;
  if ( !Value )
    return RpcImpersonateClient(0);
  v3 = Value + 5744;
  if ( *((_DWORD *)Value + 1436) )
    return 87;
  v4 = (struct _SecHandle *)*((_QWORD *)Value + 717);
  if ( v4 )
  {
    if ( !*((_QWORD *)v1 + 741) )
    {
      if ( (*((_DWORD *)v1 + 1403) & 0x200000) != 0 )
      {
        v5 = (void *)ADAMGetProxyToken(v1);
        if ( v5 )
        {
          if ( !ImpersonateLoggedOnUser(v5) )
            return GetLastError();
          *v3 = 5;
          return 0;
        }
        return 1368;
      }
      if ( !ImpersonateSecurityContext(v4) )
      {
        *v3 = 3;
        return 0;
      }
      return 1368;
    }
    return 87;
  }
  if ( *((_QWORD *)v1 + 741) )
  {
    v6 = (PCtxtHandle *)TlsGetValue(dwTSindex);
    if ( !ImpersonateSecurityContext(v6[741]) )
    {
      *v3 = 4;
      return 0;
    }
    return 1368;
  }
  result = RpcImpersonateClient(0);
  if ( result )
  {
    if ( result == 1725 || result == 1764 )
    {
      if ( *(_DWORD *)gfADAM || gfRunningAsMkdit )
      {
        CurrentThread = GetCurrentThread();
        if ( !ImpersonateAnonymousToken(CurrentThread) )
          return GetLastError();
      }
      else if ( (int)SamIImpersonateNullSession((unsigned int)(result - 1725)) < 0 )
      {
        return 1368;
      }
      *v3 = 2;
      return 0;
    }
  }
  else
  {
    *v3 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800f80e0  push    rdi
0x1800f80e2  sub     rsp, 30h
0x1800f80e6  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1800f80ec  call    cs:__imp_TlsGetValue
0x1800f80f2  mov     rcx, rax; BindingHandle
0x1800f80f5  test    rax, rax
0x1800f80f8  jnz     short loc_1800F8114
0x1800f80fa  call    cs:__imp_RpcImpersonateClient
0x1800f8100  mov     [rsp+38h+var_18], eax
0x1800f8104  jmp     short loc_1800F810F
0x1800f8106  mov     eax, 558h
0x1800f810b  mov     [rsp+38h+var_18], eax
0x1800f810f  jmp     loc_1800F824B
0x1800f8114  lea     rdi, [rax+1670h]
0x1800f811b  mov     [rsp+38h+arg_0], rdi
0x1800f8120  cmp     dword ptr [rdi], 0
0x1800f8123  jnz     loc_1800F8246
0x1800f8129  mov     rax, [rax+1668h]
0x1800f8130  test    rax, rax
0x1800f8133  jz      short loc_1800F8199
0x1800f8135  cmp     qword ptr [rcx+1728h], 0
0x1800f813d  jnz     loc_1800F8246
0x1800f8143  test    rax, rax
0x1800f8146  jz      short loc_1800F8199
0x1800f8148  test    dword ptr [rcx+15ECh], 200000h
0x1800f8152  jz      short loc_1800F8184
0x1800f8154  call    ADAMGetProxyToken
0x1800f8159  test    rax, rax
0x1800f815c  jz      short loc_1800F81C8
0x1800f815e  mov     rcx, rax; hToken
0x1800f8161  call    cs:__imp_ImpersonateLoggedOnUser
0x1800f8167  test    eax, eax
0x1800f8169  jnz     short loc_1800F8177
0x1800f816b  add     rsp, 30h
0x1800f816f  pop     rdi
0x1800f8170  jmp     cs:__imp_GetLastError
0x1800f8177  mov     dword ptr [rdi], 5
0x1800f817d  xor     eax, eax
0x1800f817f  jmp     loc_1800F824B
0x1800f8184  mov     rcx, rax; phContext
0x1800f8187  call    cs:__imp_ImpersonateSecurityContext
0x1800f818d  test    eax, eax
0x1800f818f  jnz     short loc_1800F81C8
0x1800f8191  mov     dword ptr [rdi], 3
0x1800f8197  jmp     short loc_1800F817D
0x1800f8199  cmp     qword ptr [rcx+1728h], 0
0x1800f81a1  jz      short loc_1800F81CF
0x1800f81a3  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1800f81a9  call    cs:__imp_TlsGetValue
0x1800f81af  mov     rcx, [rax+1728h]; phContext
0x1800f81b6  call    cs:__imp_ImpersonateSecurityContext
0x1800f81bc  test    eax, eax
0x1800f81be  jnz     short loc_1800F81C8
0x1800f81c0  mov     dword ptr [rdi], 4
0x1800f81c6  jmp     short loc_1800F817D
0x1800f81c8  mov     eax, 558h
0x1800f81cd  jmp     short loc_1800F824B
0x1800f81cf  xor     ecx, ecx; BindingHandle
0x1800f81d1  call    cs:__imp_RpcImpersonateClient
0x1800f81d7  mov     [rsp+38h+var_18], eax
0x1800f81db  jmp     short loc_1800F81EB
0x1800f81dd  mov     eax, 558h
0x1800f81e2  mov     [rsp+38h+var_18], eax
0x1800f81e6  mov     rdi, [rsp+38h+arg_0]
0x1800f81eb  mov     ecx, eax
0x1800f81ed  test    eax, eax
0x1800f81ef  jz      short loc_1800F823E
0x1800f81f1  sub     ecx, 6BDh
0x1800f81f7  jz      short loc_1800F81FE
0x1800f81f9  cmp     ecx, 27h ; '''
0x1800f81fc  jnz     short loc_1800F824B
0x1800f81fe  cmp     cs:gfADAM, 0
0x1800f8205  jnz     short loc_1800F821C
0x1800f8207  cmp     cs:gfRunningAsMkdit, 0
0x1800f820e  jnz     short loc_1800F821C
0x1800f8210  call    cs:__imp_SamIImpersonateNullSession
0x1800f8216  test    eax, eax
0x1800f8218  js      short loc_1800F81C8
0x1800f821a  jmp     short loc_1800F8233
0x1800f821c  call    cs:__imp_GetCurrentThread
0x1800f8222  mov     rcx, rax; ThreadHandle
0x1800f8225  call    cs:__imp_ImpersonateAnonymousToken
0x1800f822b  test    eax, eax
0x1800f822d  jz      loc_1800F816B
0x1800f8233  mov     dword ptr [rdi], 2
0x1800f8239  jmp     loc_1800F817D
0x1800f823e  mov     dword ptr [rdi], 1
0x1800f8244  jmp     short loc_1800F824B
0x1800f8246  mov     eax, 57h ; 'W'
0x1800f824b  add     rsp, 30h
0x1800f824f  pop     rdi
0x1800f8250  retn
0x18045d027  push    rbp
0x18045d029  sub     rsp, 20h
0x18045d02d  mov     rbp, rdx
0x18045d030  mov     rdx, [rcx]
0x18045d033  mov     edx, [rdx]
0x18045d035  mov     r8d, 32E00C1h
0x18045d03b  call    DoHandleAllExceptions
0x18045d040  nop
0x18045d041  add     rsp, 20h
0x18045d045  pop     rbp
0x18045d046  retn
0x18045d048  push    rbp
0x18045d04a  sub     rsp, 20h
0x18045d04e  mov     rbp, rdx
0x18045d051  mov     rdx, [rcx]
0x18045d054  mov     edx, [rdx]
0x18045d056  mov     r8d, 32E00FFh
0x18045d05c  call    DoHandleAllExceptions
0x18045d061  nop
0x18045d062  add     rsp, 20h
0x18045d066  pop     rbp
0x18045d067  retn
```

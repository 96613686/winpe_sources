# EfsRpcFlushEfsCache

- ea: `0x1800065a0`
- end: `0x1800066fc`
- name: `EfsRpcFlushEfsCache`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000356c`
- `0x180003604`
- `0x1800065a0`
- `0x180007ae8`
- `0x18000b308`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006698`
- `RPCRT4!RpcRevertToSelf` at `0x1800066e3`
- `RPCRT4!RpcRevertToSelf` at `0x1800066e3`
- `RPCRT4!RpcImpersonateClient` at `0x180006646`
- `RPCRT4!RpcImpersonateClient` at `0x180006646`
- `EFSCORE!EfsDllSsoFlushUserCache` at `0x1800066af`
- `EFSCORE!EfsDllSsoFlushUserCache` at `0x1800066af`
- `EFSCORE!EfsDllDisabled` at `0x1800065eb`
- `EFSCORE!EfsDllDisabled` at `0x1800065eb`
- `EFSCORE!EfsDllFreeUserInfo` at `0x1800066dd`
- `EFSCORE!EfsDllFreeUserInfo` at `0x1800066dd`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000668e`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000668e`

## pseudocode

```c
__int64 __fastcall EfsRpcFlushEfsCache(__int64 a1)
{
  __int64 v2; // rcx
  DWORD LastError; // ebx
  __int64 v4; // rcx
  DWORD v5; // eax
  int v6; // ecx
  RPC_STATUS v7; // eax
  int v8; // ecx
  DWORD IsValidNetworkProtSeq; // eax
  int v10; // ecx
  int v11; // ecx
  DWORD v12; // eax
  int v13; // ecx
  _BYTE v15[120]; // [rsp+30h] [rbp-78h] BYREF

  memset_0(v15, 0, 0x70u);
  if ( EfsServerInitialized )
  {
    if ( (unsigned __int8)EfsDllDisabled(v2) )
    {
      fnEfsLogTrace0(v4, EFS_SL_EFS_DISABLED, 6, 2318);
      return 6015;
    }
    else
    {
      v5 = EfsEnforceClientAuthentication();
      LastError = v5;
      if ( v5 )
      {
        fnEfsLogTrace1(v6, (unsigned int)EFS_API_ERROR, v5, 6, 20);
      }
      else
      {
        v7 = RpcImpersonateClient(0);
        LastError = v7;
        if ( v7 )
        {
          fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v7, 6, 25);
        }
        else
        {
          IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
          LastError = IsValidNetworkProtSeq;
          if ( IsValidNetworkProtSeq )
          {
            fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 35);
          }
          else if ( (unsigned __int8)EfsDllGetUserInfo(v15) )
          {
            v12 = EfsDllSsoFlushUserCache(v15);
            LastError = v12;
            if ( v12 )
              fnEfsLogTrace1(v13, (unsigned int)EFS_API_ERROR, v12, 6, 47);
            EfsDllFreeUserInfo(v15);
          }
          else
          {
            LastError = GetLastError();
            fnEfsLogTrace1(v11, (unsigned int)EFS_API_ERROR, LastError, 6, 41);
          }
          RpcRevertToSelf();
        }
      }
    }
  }
  else
  {
    fnEfsLogTrace0(v2, EFS_SL_NOT_YET_INITIALIZED, 6, 2312);
    return 50;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800065a0  mov     [rsp+arg_0], rbx
0x1800065a5  push    rdi
0x1800065a6  sub     rsp, 0A0h
0x1800065ad  xor     edx, edx; Val
0x1800065af  mov     rdi, rcx
0x1800065b2  lea     rcx, [rsp+0A8h+var_78]; void *
0x1800065b7  lea     r8d, [rdx+70h]; Size
0x1800065bb  call    memset_0
0x1800065c0  cmp     cs:EfsServerInitialized, 0
0x1800065c7  jnz     short loc_1800065EB
0x1800065c9  mov     r9d, 908h
0x1800065cf  lea     rdx, EFS_SL_NOT_YET_INITIALIZED
0x1800065d6  mov     r8d, 6
0x1800065dc  call    fnEfsLogTrace0
0x1800065e1  mov     ebx, 32h ; '2'
0x1800065e6  jmp     loc_1800066E9
0x1800065eb  call    cs:__imp_EfsDllDisabled
0x1800065f1  test    al, al
0x1800065f3  jz      short loc_180006617
0x1800065f5  mov     r9d, 90Eh
0x1800065fb  lea     rdx, EFS_SL_EFS_DISABLED
0x180006602  mov     r8d, 6
0x180006608  call    fnEfsLogTrace0
0x18000660d  mov     ebx, 177Fh
0x180006612  jmp     loc_1800066E9
0x180006617  call    EfsEnforceClientAuthentication
0x18000661c  mov     ebx, eax
0x18000661e  test    eax, eax
0x180006620  jz      short loc_180006644
0x180006622  mov     [rsp+0A8h+var_88], 914h
0x18000662a  mov     r9d, 6
0x180006630  lea     rdx, EFS_API_ERROR
0x180006637  mov     r8d, eax
0x18000663a  call    fnEfsLogTrace1
0x18000663f  jmp     loc_1800066E9
0x180006644  xor     ecx, ecx; BindingHandle
0x180006646  call    cs:__imp_RpcImpersonateClient
0x18000664c  mov     ebx, eax
0x18000664e  test    eax, eax
0x180006650  jz      short loc_18000665C
0x180006652  mov     [rsp+0A8h+var_88], 919h
0x18000665a  jmp     short loc_18000662A
0x18000665c  mov     rcx, rdi
0x18000665f  call    EfspIsValidNetworkProtSeq
0x180006664  mov     ebx, eax
0x180006666  test    eax, eax
0x180006668  jz      short loc_180006689
0x18000666a  mov     [rsp+0A8h+var_88], 923h
0x180006672  mov     r9d, 6
0x180006678  lea     rdx, EFS_API_ERROR
0x18000667f  mov     r8d, eax
0x180006682  call    fnEfsLogTrace1
0x180006687  jmp     short loc_1800066E3
0x180006689  lea     rcx, [rsp+0A8h+var_78]
0x18000668e  call    cs:__imp_EfsDllGetUserInfo
0x180006694  test    al, al
0x180006696  jnz     short loc_1800066AA
0x180006698  call    cs:__imp_GetLastError
0x18000669e  mov     ebx, eax
0x1800066a0  mov     [rsp+0A8h+var_88], 929h
0x1800066a8  jmp     short loc_180006672
0x1800066aa  lea     rcx, [rsp+0A8h+var_78]
0x1800066af  call    cs:__imp_EfsDllSsoFlushUserCache
0x1800066b5  mov     ebx, eax
0x1800066b7  test    eax, eax
0x1800066b9  jz      short loc_1800066D8
0x1800066bb  mov     r9d, 6
0x1800066c1  mov     [rsp+0A8h+var_88], 92Fh
0x1800066c9  mov     r8d, eax
0x1800066cc  lea     rdx, EFS_API_ERROR
0x1800066d3  call    fnEfsLogTrace1
0x1800066d8  lea     rcx, [rsp+0A8h+var_78]
0x1800066dd  call    cs:__imp_EfsDllFreeUserInfo
0x1800066e3  call    cs:__imp_RpcRevertToSelf
0x1800066e9  mov     eax, ebx
0x1800066eb  mov     rbx, [rsp+0A8h+arg_0]
0x1800066f3  add     rsp, 0A0h
0x1800066fa  pop     rdi
0x1800066fb  retn
```

# EfsRpcFlushEfsCache

- ea: `0x180006bf0`
- end: `0x180006d77`
- name: `EfsRpcFlushEfsCache`
- size: `391`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003714`
- `0x1800037b8`
- `0x180006bf0`
- `0x180008404`
- `0x18000bf0c`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cfa`
- `RPCRT4!RpcRevertToSelf` at `0x180006d57`
- `RPCRT4!RpcRevertToSelf` at `0x180006d57`
- `RPCRT4!RpcImpersonateClient` at `0x180006c9c`
- `RPCRT4!RpcImpersonateClient` at `0x180006c9c`
- `EFSCORE!EfsDllSsoFlushUserCache` at `0x180006d17`
- `EFSCORE!EfsDllSsoFlushUserCache` at `0x180006d17`
- `EFSCORE!EfsDllDisabled` at `0x180006c3b`
- `EFSCORE!EfsDllDisabled` at `0x180006c3b`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006d4b`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006d4b`
- `EFSCORE!EfsDllGetUserInfo` at `0x180006cea`
- `EFSCORE!EfsDllGetUserInfo` at `0x180006cea`

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
0x180006bf0  mov     [rsp+arg_0], rbx
0x180006bf5  push    rdi
0x180006bf6  sub     rsp, 0A0h
0x180006bfd  xor     edx, edx; Val
0x180006bff  mov     rdi, rcx
0x180006c02  lea     rcx, [rsp+0A8h+var_78]; void *
0x180006c07  lea     r8d, [rdx+70h]; Size
0x180006c0b  call    memset_0
0x180006c10  cmp     cs:EfsServerInitialized, 0
0x180006c17  jnz     short loc_180006C3B
0x180006c19  mov     r9d, 908h
0x180006c1f  lea     rdx, EFS_SL_NOT_YET_INITIALIZED
0x180006c26  mov     r8d, 6
0x180006c2c  call    fnEfsLogTrace0
0x180006c31  mov     ebx, 32h ; '2'
0x180006c36  jmp     loc_180006D63
0x180006c3b  call    cs:__imp_EfsDllDisabled
0x180006c42  nop     dword ptr [rax+rax+00h]
0x180006c47  test    al, al
0x180006c49  jz      short loc_180006C6D
0x180006c4b  mov     r9d, 90Eh
0x180006c51  lea     rdx, EFS_SL_EFS_DISABLED
0x180006c58  mov     r8d, 6
0x180006c5e  call    fnEfsLogTrace0
0x180006c63  mov     ebx, 177Fh
0x180006c68  jmp     loc_180006D63
0x180006c6d  call    EfsEnforceClientAuthentication
0x180006c72  mov     ebx, eax
0x180006c74  test    eax, eax
0x180006c76  jz      short loc_180006C9A
0x180006c78  mov     [rsp+0A8h+var_88], 914h
0x180006c80  mov     r9d, 6
0x180006c86  lea     rdx, EFS_API_ERROR
0x180006c8d  mov     r8d, eax
0x180006c90  call    fnEfsLogTrace1
0x180006c95  jmp     loc_180006D63
0x180006c9a  xor     ecx, ecx; BindingHandle
0x180006c9c  call    cs:__imp_RpcImpersonateClient
0x180006ca3  nop     dword ptr [rax+rax+00h]
0x180006ca8  mov     ebx, eax
0x180006caa  test    eax, eax
0x180006cac  jz      short loc_180006CB8
0x180006cae  mov     [rsp+0A8h+var_88], 919h
0x180006cb6  jmp     short loc_180006C80
0x180006cb8  mov     rcx, rdi
0x180006cbb  call    EfspIsValidNetworkProtSeq
0x180006cc0  mov     ebx, eax
0x180006cc2  test    eax, eax
0x180006cc4  jz      short loc_180006CE5
0x180006cc6  mov     [rsp+0A8h+var_88], 923h
0x180006cce  mov     r9d, 6
0x180006cd4  lea     rdx, EFS_API_ERROR
0x180006cdb  mov     r8d, eax
0x180006cde  call    fnEfsLogTrace1
0x180006ce3  jmp     short loc_180006D57
0x180006ce5  lea     rcx, [rsp+0A8h+var_78]
0x180006cea  call    cs:__imp_EfsDllGetUserInfo
0x180006cf1  nop     dword ptr [rax+rax+00h]
0x180006cf6  test    al, al
0x180006cf8  jnz     short loc_180006D12
0x180006cfa  call    cs:__imp_GetLastError
0x180006d01  nop     dword ptr [rax+rax+00h]
0x180006d06  mov     ebx, eax
0x180006d08  mov     [rsp+0A8h+var_88], 929h
0x180006d10  jmp     short loc_180006CCE
0x180006d12  lea     rcx, [rsp+0A8h+var_78]
0x180006d17  call    cs:__imp_EfsDllSsoFlushUserCache
0x180006d1e  nop     dword ptr [rax+rax+00h]
0x180006d23  mov     ebx, eax
0x180006d25  test    eax, eax
0x180006d27  jz      short loc_180006D46
0x180006d29  mov     r9d, 6
0x180006d2f  mov     [rsp+0A8h+var_88], 92Fh
0x180006d37  mov     r8d, eax
0x180006d3a  lea     rdx, EFS_API_ERROR
0x180006d41  call    fnEfsLogTrace1
0x180006d46  lea     rcx, [rsp+0A8h+var_78]
0x180006d4b  call    cs:__imp_EfsDllFreeUserInfo
0x180006d52  nop     dword ptr [rax+rax+00h]
0x180006d57  call    cs:__imp_RpcRevertToSelf
0x180006d5e  nop     dword ptr [rax+rax+00h]
0x180006d63  mov     eax, ebx
0x180006d65  mov     rbx, [rsp+0A8h+arg_0]
0x180006d6d  add     rsp, 0A0h
0x180006d74  pop     rdi
0x180006d75  retn
```

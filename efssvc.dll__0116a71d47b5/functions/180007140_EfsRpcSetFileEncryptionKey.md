# EfsRpcSetFileEncryptionKey

- ea: `0x180007140`
- end: `0x18000727b`
- name: `EfsRpcSetFileEncryptionKey`
- size: `315`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x180003604`
- `0x180007140`
- `0x18000b308`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000720f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000722a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000720f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000722a`
- `RPCRT4!RpcRevertToSelf` at `0x180007260`
- `RPCRT4!RpcRevertToSelf` at `0x180007260`
- `RPCRT4!RpcImpersonateClient` at `0x1800071ea`
- `RPCRT4!RpcImpersonateClient` at `0x1800071ea`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800071a3`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800071a3`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000724f`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000724f`
- `EFSCORE!EfsDllDisabled` at `0x180007188`
- `EFSCORE!EfsDllDisabled` at `0x180007188`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000725a`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000725a`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007205`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007205`
- `EFSCORE!EfsDllSetFileEncryptionKeySrv` at `0x180007242`
- `EFSCORE!EfsDllSetFileEncryptionKeySrv` at `0x180007242`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007220`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007220`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180007174`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180007174`

## pseudocode

```c
__int64 __fastcall EfsRpcSetFileEncryptionKey(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v7; // rcx
  DWORD LastError; // ebx
  DWORD v9; // eax
  int v10; // ecx
  RPC_STATUS v11; // eax
  int v12; // ecx
  __int64 v13; // rdx
  unsigned int ClientLocalFlag[4]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v16[152]; // [rsp+40h] [rbp-98h] BYREF

  ClientLocalFlag[0] = 0;
  memset_0(v16, 0, 0x70u);
  if ( (unsigned __int8)EfsDllIsNonEfsSKU(L"feclient-EfsEnabled") )
  {
    return 50;
  }
  else if ( (unsigned __int8)EfsDllDisabled(v7) )
  {
    return 6015;
  }
  else if ( I_RpcBindingIsClientLocal(0, ClientLocalFlag) || !ClientLocalFlag[0] )
  {
    return 5;
  }
  else
  {
    v9 = EfsEnforceClientAuthentication();
    LastError = v9;
    if ( v9 )
    {
      fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 233);
    }
    else
    {
      v11 = RpcImpersonateClient(0);
      LastError = v11;
      if ( v11 )
      {
        fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v11, 6, 238);
      }
      else
      {
        if ( (unsigned __int8)EfsDllGetUserInfo(v16) )
        {
          LOBYTE(v13) = 1;
          if ( (unsigned int)EfsDllLoadUserProfile(v16, v13) )
          {
            LastError = EfsDllSetFileEncryptionKeySrv(v16, a2, a3, a4);
            EfsDllUnloadUserProfile(v16);
          }
          else
          {
            LastError = GetLastError();
          }
          EfsDllFreeUserInfo(v16);
        }
        else
        {
          LastError = GetLastError();
        }
        RpcRevertToSelf();
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180007140  push    rbx
0x180007142  push    rbp
0x180007143  push    rsi
0x180007144  push    rdi
0x180007145  sub     rsp, 0B8h
0x18000714c  mov     rbp, rdx
0x18000714f  mov     [rsp+0D8h+ClientLocalFlag], 0
0x180007157  xor     edx, edx; Val
0x180007159  lea     rcx, [rsp+0D8h+var_98]; void *
0x18000715e  mov     esi, r8d
0x180007161  mov     edi, r9d
0x180007164  lea     r8d, [rdx+70h]; Size
0x180007168  call    memset_0
0x18000716d  lea     rcx, aFeclientEfsena_0; "feclient-EfsEnabled"
0x180007174  call    cs:__imp_EfsDllIsNonEfsSKU
0x18000717a  test    al, al
0x18000717c  jz      short loc_180007188
0x18000717e  mov     ebx, 32h ; '2'
0x180007183  jmp     loc_18000726D
0x180007188  call    cs:__imp_EfsDllDisabled
0x18000718e  test    al, al
0x180007190  jz      short loc_18000719C
0x180007192  mov     ebx, 177Fh
0x180007197  jmp     loc_18000726D
0x18000719c  lea     rdx, [rsp+0D8h+ClientLocalFlag]; ClientLocalFlag
0x1800071a1  xor     ecx, ecx; BindingHandle
0x1800071a3  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800071a9  test    eax, eax
0x1800071ab  jnz     loc_180007268
0x1800071b1  cmp     [rsp+0D8h+ClientLocalFlag], eax
0x1800071b5  jz      loc_180007268
0x1800071bb  call    EfsEnforceClientAuthentication
0x1800071c0  mov     ebx, eax
0x1800071c2  test    eax, eax
0x1800071c4  jz      short loc_1800071E8
0x1800071c6  mov     [rsp+0D8h+var_B8], 6E9h
0x1800071ce  mov     r9d, 6
0x1800071d4  lea     rdx, EFS_API_ERROR
0x1800071db  mov     r8d, eax
0x1800071de  call    fnEfsLogTrace1
0x1800071e3  jmp     loc_18000726D
0x1800071e8  xor     ecx, ecx; BindingHandle
0x1800071ea  call    cs:__imp_RpcImpersonateClient
0x1800071f0  mov     ebx, eax
0x1800071f2  test    eax, eax
0x1800071f4  jz      short loc_180007200
0x1800071f6  mov     [rsp+0D8h+var_B8], 6EEh
0x1800071fe  jmp     short loc_1800071CE
0x180007200  lea     rcx, [rsp+0D8h+var_98]
0x180007205  call    cs:__imp_EfsDllGetUserInfo
0x18000720b  test    al, al
0x18000720d  jnz     short loc_180007219
0x18000720f  call    cs:__imp_GetLastError
0x180007215  mov     ebx, eax
0x180007217  jmp     short loc_180007260
0x180007219  mov     dl, 1
0x18000721b  lea     rcx, [rsp+0D8h+var_98]
0x180007220  call    cs:__imp_EfsDllLoadUserProfile
0x180007226  test    eax, eax
0x180007228  jnz     short loc_180007234
0x18000722a  call    cs:__imp_GetLastError
0x180007230  mov     ebx, eax
0x180007232  jmp     short loc_180007255
0x180007234  mov     r9d, edi
0x180007237  lea     rcx, [rsp+0D8h+var_98]
0x18000723c  mov     r8d, esi
0x18000723f  mov     rdx, rbp
0x180007242  call    cs:__imp_EfsDllSetFileEncryptionKeySrv
0x180007248  lea     rcx, [rsp+0D8h+var_98]
0x18000724d  mov     ebx, eax
0x18000724f  call    cs:__imp_EfsDllUnloadUserProfile
0x180007255  lea     rcx, [rsp+0D8h+var_98]
0x18000725a  call    cs:__imp_EfsDllFreeUserInfo
0x180007260  call    cs:__imp_RpcRevertToSelf
0x180007266  jmp     short loc_18000726D
0x180007268  mov     ebx, 5
0x18000726d  mov     eax, ebx
0x18000726f  add     rsp, 0B8h
0x180007276  pop     rdi
0x180007277  pop     rsi
0x180007278  pop     rbp
0x180007279  pop     rbx
0x18000727a  retn
```

# s_SSCatDBPrepareForCall

- ea: `0x18001cb50`
- end: `0x18001cc8c`
- name: `s_SSCatDBPrepareForCall`
- size: `316`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007fb0`
- `0x18000a59c`
- `0x18001cb50`
- `0x18001cf60`
- `0x18001da60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cb93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cbc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cbf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cc4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cc74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cb93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cbc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cbf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cc4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cc74`
- `RPCRT4!RpcRevertToSelf` at `0x18001cbe6`
- `RPCRT4!RpcRevertToSelf` at `0x18001cc3d`
- `RPCRT4!RpcRevertToSelf` at `0x18001cbe6`
- `RPCRT4!RpcRevertToSelf` at `0x18001cc3d`
- `RPCRT4!RpcImpersonateClient` at `0x18001cbb4`
- `RPCRT4!RpcImpersonateClient` at `0x18001cbb4`

## pseudocode

```c
__int64 __fastcall s_SSCatDBPrepareForCall(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *a2)
{
  DWORD v4; // eax
  unsigned int v5; // edx
  unsigned __int16 *v6; // rcx
  unsigned int v7; // r8d
  RPC_STATUS v8; // eax
  int v9; // esi
  RPC_STATUS v10; // eax
  unsigned int v11; // edx
  unsigned __int16 *v12; // rcx
  DWORD LastError; // ebx
  DWORD v14; // ecx
  unsigned int v15; // edx
  unsigned __int16 *v16; // rcx
  int v18; // [rsp+28h] [rbp-10h]

  if ( !BindingHandle || !_CatDBDVerifyGUIDString(a2) )
  {
    v14 = 87;
    goto LABEL_16;
  }
  v4 = _CatDBCanWriteToPathWithImpersonation(BindingHandle, g_pwszCatalogFileBaseDirectory);
  if ( !v4 )
  {
    v8 = RpcImpersonateClient(BindingHandle);
    if ( v8 )
    {
      SetLastError(v8);
      v7 = 7127;
      goto LABEL_5;
    }
    v9 = 1;
    if ( !(unsigned int)_CatDBEnsureDirExists(g_pwszCatalogFileBaseDirectory, a2) )
      goto LABEL_13;
    v10 = RpcRevertToSelf();
    if ( v10 )
    {
      SetLastError(v10);
      ErrLog_LogError(v12, v11, 0x1BE2u, 0, 0, v18);
      LastError = GetLastError();
LABEL_14:
      RpcRevertToSelf();
      goto LABEL_18;
    }
    v9 = 0;
    if ( !(unsigned int)_CatDBEnsureDirExists(g_pwszDatabaseFileBaseDirectory, a2) )
    {
LABEL_13:
      LastError = GetLastError();
      if ( !v9 )
        goto LABEL_18;
      goto LABEL_14;
    }
    v14 = 0;
LABEL_16:
    SetLastError(v14);
    goto LABEL_17;
  }
  SetLastError(v4);
  v7 = 7120;
LABEL_5:
  ErrLog_LogError(v6, v5, v7, 0, 0, v18);
LABEL_17:
  LastError = GetLastError();
LABEL_18:
  if ( LastError )
    ErrLog_LogError(v16, v15, 0x1BF6u, 0, 0, v18);
  SetLastError(LastError);
  return LastError;
}

```

## disassembly

```asm
0x18001cb50  mov     [rsp+arg_0], rbx
0x18001cb55  mov     [rsp+arg_8], rsi
0x18001cb5a  push    rdi
0x18001cb5b  sub     rsp, 30h
0x18001cb5f  mov     rdi, rdx
0x18001cb62  mov     rbx, rcx
0x18001cb65  test    rcx, rcx
0x18001cb68  jz      loc_18001CC45
0x18001cb6e  mov     rcx, rdx; unsigned __int16 *
0x18001cb71  call    ?_CatDBDVerifyGUIDString@@YAHPEBG@Z; _CatDBDVerifyGUIDString(ushort const *)
0x18001cb76  test    eax, eax
0x18001cb78  jz      loc_18001CC45
0x18001cb7e  mov     rdx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; lpFileName
0x18001cb85  mov     rcx, rbx; BindingHandle
0x18001cb88  call    ?_CatDBCanWriteToPathWithImpersonation@@YAKPEAXPEBG@Z; _CatDBCanWriteToPathWithImpersonation(void *,ushort const *)
0x18001cb8d  test    eax, eax
0x18001cb8f  jz      short loc_18001CBB1
0x18001cb91  mov     ecx, eax; dwErrCode
0x18001cb93  call    cs:__imp_SetLastError
0x18001cb99  mov     r8d, 1BD0h; unsigned int
0x18001cb9f  xor     r9d, r9d; unsigned int
0x18001cba2  mov     [rsp+38h+var_18], r9d; int
0x18001cba7  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001cbac  jmp     loc_18001CC50
0x18001cbb1  mov     rcx, rbx; BindingHandle
0x18001cbb4  call    cs:__imp_RpcImpersonateClient
0x18001cbba  test    eax, eax
0x18001cbbc  jz      short loc_18001CBCE
0x18001cbbe  mov     ecx, eax; dwErrCode
0x18001cbc0  call    cs:__imp_SetLastError
0x18001cbc6  mov     r8d, 1BD7h
0x18001cbcc  jmp     short loc_18001CB9F
0x18001cbce  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; lpFileName
0x18001cbd5  mov     rdx, rdi; unsigned __int16 *
0x18001cbd8  mov     esi, 1
0x18001cbdd  call    ?_CatDBEnsureDirExists@@YAHPEBG0@Z; _CatDBEnsureDirExists(ushort const *,ushort const *)
0x18001cbe2  test    eax, eax
0x18001cbe4  jz      short loc_18001CC31
0x18001cbe6  call    cs:__imp_RpcRevertToSelf
0x18001cbec  test    eax, eax
0x18001cbee  jz      short loc_18001CC18
0x18001cbf0  mov     ecx, eax; dwErrCode
0x18001cbf2  call    cs:__imp_SetLastError
0x18001cbf8  xor     r9d, r9d; unsigned int
0x18001cbfb  mov     [rsp+38h+var_18], 0; int
0x18001cc03  mov     r8d, 1BE2h; unsigned int
0x18001cc09  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001cc0e  call    cs:__imp_GetLastError
0x18001cc14  mov     ebx, eax
0x18001cc16  jmp     short loc_18001CC3D
0x18001cc18  mov     rcx, cs:?g_pwszDatabaseFileBaseDirectory@@3PEAGEA; lpFileName
0x18001cc1f  mov     rdx, rdi; unsigned __int16 *
0x18001cc22  xor     esi, esi
0x18001cc24  call    ?_CatDBEnsureDirExists@@YAHPEBG0@Z; _CatDBEnsureDirExists(ushort const *,ushort const *)
0x18001cc29  test    eax, eax
0x18001cc2b  jz      short loc_18001CC31
0x18001cc2d  xor     ecx, ecx
0x18001cc2f  jmp     short loc_18001CC4A
0x18001cc31  call    cs:__imp_GetLastError
0x18001cc37  mov     ebx, eax
0x18001cc39  test    esi, esi
0x18001cc3b  jz      short loc_18001CC58
0x18001cc3d  call    cs:__imp_RpcRevertToSelf
0x18001cc43  jmp     short loc_18001CC58
0x18001cc45  mov     ecx, 57h ; 'W'; dwErrCode
0x18001cc4a  call    cs:__imp_SetLastError
0x18001cc50  call    cs:__imp_GetLastError
0x18001cc56  mov     ebx, eax
0x18001cc58  test    ebx, ebx
0x18001cc5a  jz      short loc_18001CC72
0x18001cc5c  xor     r9d, r9d; unsigned int
0x18001cc5f  mov     [rsp+38h+var_18], 0; int
0x18001cc67  mov     r8d, 1BF6h; unsigned int
0x18001cc6d  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001cc72  mov     ecx, ebx; dwErrCode
0x18001cc74  call    cs:__imp_SetLastError
0x18001cc7a  mov     rsi, [rsp+38h+arg_8]
0x18001cc7f  mov     eax, ebx
0x18001cc81  mov     rbx, [rsp+38h+arg_0]
0x18001cc86  add     rsp, 30h
0x18001cc8a  pop     rdi
0x18001cc8b  retn
```

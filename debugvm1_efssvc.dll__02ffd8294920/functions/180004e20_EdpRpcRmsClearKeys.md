# EdpRpcRmsClearKeys

- ea: `0x180004e20`
- end: `0x180004f23`
- name: `EdpRpcRmsClearKeys`
- size: `259`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003604`
- `0x180004e20`
- `0x18000b308`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180004ee4`
- `RPCRT4!RpcRevertToSelf` at `0x180004ee4`
- `RPCRT4!RpcImpersonateClient` at `0x180004e9a`
- `RPCRT4!RpcImpersonateClient` at `0x180004e9a`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004e60`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004e60`
- `EFSCORE!EfsDllDisabled` at `0x180004e44`
- `EFSCORE!EfsDllDisabled` at `0x180004e44`
- `EFSCORE!EdpDllRmsClearKeys` at `0x180004ebb`
- `EFSCORE!EdpDllRmsClearKeys` at `0x180004ebb`

## pseudocode

```c
__int64 __fastcall EdpRpcRmsClearKeys(RPC_BINDING_HANDLE BindingHandle)
{
  unsigned int v2; // ebx
  RPC_STATUS IsClientLocal; // eax
  int v4; // ecx
  int v5; // eax
  int v6; // ecx
  RPC_STATUS v7; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // ecx
  unsigned int ClientLocalFlag; // [rsp+48h] [rbp+10h] BYREF

  ClientLocalFlag = 0;
  if ( !EfsServerInitialized )
    return (unsigned int)-2147024846;
  if ( (unsigned __int8)EfsDllDisabled(BindingHandle) )
    return (unsigned int)-2147018881;
  IsClientLocal = I_RpcBindingIsClientLocal(BindingHandle, &ClientLocalFlag);
  v2 = IsClientLocal;
  if ( IsClientLocal )
  {
    if ( IsClientLocal > 0 )
      v2 = (unsigned __int16)IsClientLocal | 0x80070000;
    goto LABEL_21;
  }
  if ( !ClientLocalFlag )
  {
    v2 = -2147024891;
LABEL_21:
    fnEfsLogTrace1(v4, (unsigned int)EFS_API_ERROR, v2, 6, 179);
    return v2;
  }
  v5 = EfsEnforceClientAuthentication();
  v2 = v5;
  if ( v5 > 0 )
    v2 = (unsigned __int16)v5 | 0x80070000;
  if ( (v2 & 0x80000000) == 0 )
  {
    v7 = RpcImpersonateClient(0);
    v2 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v2, 6, 196);
    }
    else
    {
      v9 = EdpDllRmsClearKeys();
      v2 = v9;
      if ( v9 < 0 )
        fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 204);
      RpcRevertToSelf();
    }
  }
  else
  {
    fnEfsLogTrace1(v6, (unsigned int)EFS_API_ERROR, v2, 6, 184);
  }
  return v2;
}

```

## disassembly

```asm
0x180004e20  push    rbx
0x180004e22  sub     rsp, 30h
0x180004e26  cmp     cs:EfsServerInitialized, 0
0x180004e2d  mov     rbx, rcx
0x180004e30  mov     [rsp+38h+ClientLocalFlag], 0
0x180004e38  jnz     short loc_180004E44
0x180004e3a  mov     ebx, 80070032h
0x180004e3f  jmp     loc_180004F1B
0x180004e44  call    cs:__imp_EfsDllDisabled
0x180004e4a  test    al, al
0x180004e4c  jz      short loc_180004E58
0x180004e4e  mov     ebx, 8007177Fh
0x180004e53  jmp     loc_180004F1B
0x180004e58  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x180004e5d  mov     rcx, rbx; BindingHandle
0x180004e60  call    cs:__imp_I_RpcBindingIsClientLocal
0x180004e66  mov     ebx, eax
0x180004e68  test    eax, eax
0x180004e6a  jnz     loc_180004EF3
0x180004e70  cmp     [rsp+38h+ClientLocalFlag], eax
0x180004e74  jz      short loc_180004EEC
0x180004e76  call    EfsEnforceClientAuthentication
0x180004e7b  mov     ebx, eax
0x180004e7d  test    eax, eax
0x180004e7f  jle     short loc_180004E8A
0x180004e81  movzx   ebx, ax
0x180004e84  or      ebx, 80070000h
0x180004e8a  test    ebx, ebx
0x180004e8c  jns     short loc_180004E98
0x180004e8e  mov     [rsp+38h+var_18], 0FB8h
0x180004e96  jmp     short loc_180004F06
0x180004e98  xor     ecx, ecx; BindingHandle
0x180004e9a  call    cs:__imp_RpcImpersonateClient
0x180004ea0  mov     ebx, eax
0x180004ea2  test    eax, eax
0x180004ea4  jz      short loc_180004EBB
0x180004ea6  jle     short loc_180004EB1
0x180004ea8  movzx   ebx, ax
0x180004eab  or      ebx, 80070000h
0x180004eb1  mov     [rsp+38h+var_18], 0FC4h
0x180004eb9  jmp     short loc_180004F06
0x180004ebb  call    cs:__imp_EdpDllRmsClearKeys
0x180004ec1  mov     ebx, eax
0x180004ec3  test    eax, eax
0x180004ec5  jns     short loc_180004EE4
0x180004ec7  mov     r9d, 6
0x180004ecd  mov     [rsp+38h+var_18], 0FCCh
0x180004ed5  mov     r8d, eax
0x180004ed8  lea     rdx, EFS_API_ERROR
0x180004edf  call    fnEfsLogTrace1
0x180004ee4  call    cs:__imp_RpcRevertToSelf
0x180004eea  jmp     short loc_180004F1B
0x180004eec  mov     ebx, 80070005h
0x180004ef1  jmp     short loc_180004EFE
0x180004ef3  jle     short loc_180004EFE
0x180004ef5  movzx   ebx, ax
0x180004ef8  or      ebx, 80070000h
0x180004efe  mov     [rsp+38h+var_18], 0FB3h
0x180004f06  mov     r9d, 6
0x180004f0c  lea     rdx, EFS_API_ERROR
0x180004f13  mov     r8d, ebx
0x180004f16  call    fnEfsLogTrace1
0x180004f1b  mov     eax, ebx
0x180004f1d  add     rsp, 30h
0x180004f21  pop     rbx
0x180004f22  retn
```

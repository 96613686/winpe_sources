# EdpRpcRmsClearKeys

- ea: `0x180005180`
- end: `0x1800052a9`
- name: `EdpRpcRmsClearKeys`
- size: `297`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800037b8`
- `0x180005180`
- `0x18000bf0c`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180005263`
- `RPCRT4!RpcRevertToSelf` at `0x180005263`
- `RPCRT4!RpcImpersonateClient` at `0x18000520d`
- `RPCRT4!RpcImpersonateClient` at `0x18000520d`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800051c6`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800051c6`
- `EFSCORE!EfsDllDisabled` at `0x1800051a4`
- `EFSCORE!EfsDllDisabled` at `0x1800051a4`
- `EFSCORE!EdpDllRmsClearKeys` at `0x180005234`
- `EFSCORE!EdpDllRmsClearKeys` at `0x180005234`

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
0x180005180  push    rbx
0x180005182  sub     rsp, 30h
0x180005186  cmp     cs:EfsServerInitialized, 0
0x18000518d  mov     rbx, rcx
0x180005190  mov     [rsp+38h+ClientLocalFlag], 0
0x180005198  jnz     short loc_1800051A4
0x18000519a  mov     ebx, 80070032h
0x18000519f  jmp     loc_1800052A0
0x1800051a4  call    cs:__imp_EfsDllDisabled
0x1800051ab  nop     dword ptr [rax+rax+00h]
0x1800051b0  test    al, al
0x1800051b2  jz      short loc_1800051BE
0x1800051b4  mov     ebx, 8007177Fh
0x1800051b9  jmp     loc_1800052A0
0x1800051be  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x1800051c3  mov     rcx, rbx; BindingHandle
0x1800051c6  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800051cd  nop     dword ptr [rax+rax+00h]
0x1800051d2  mov     ebx, eax
0x1800051d4  test    eax, eax
0x1800051d6  jnz     loc_180005278
0x1800051dc  cmp     [rsp+38h+ClientLocalFlag], eax
0x1800051e0  jz      loc_180005271
0x1800051e6  call    EfsEnforceClientAuthentication
0x1800051eb  mov     ebx, eax
0x1800051ed  test    eax, eax
0x1800051ef  jle     short loc_1800051FA
0x1800051f1  movzx   ebx, ax
0x1800051f4  or      ebx, 80070000h
0x1800051fa  test    ebx, ebx
0x1800051fc  jns     short loc_18000520B
0x1800051fe  mov     [rsp+38h+var_18], 0FB8h
0x180005206  jmp     loc_18000528B
0x18000520b  xor     ecx, ecx; BindingHandle
0x18000520d  call    cs:__imp_RpcImpersonateClient
0x180005214  nop     dword ptr [rax+rax+00h]
0x180005219  mov     ebx, eax
0x18000521b  test    eax, eax
0x18000521d  jz      short loc_180005234
0x18000521f  jle     short loc_18000522A
0x180005221  movzx   ebx, ax
0x180005224  or      ebx, 80070000h
0x18000522a  mov     [rsp+38h+var_18], 0FC4h
0x180005232  jmp     short loc_18000528B
0x180005234  call    cs:__imp_EdpDllRmsClearKeys
0x18000523b  nop     dword ptr [rax+rax+00h]
0x180005240  mov     ebx, eax
0x180005242  test    eax, eax
0x180005244  jns     short loc_180005263
0x180005246  mov     r9d, 6
0x18000524c  mov     [rsp+38h+var_18], 0FCCh
0x180005254  mov     r8d, eax
0x180005257  lea     rdx, EFS_API_ERROR
0x18000525e  call    fnEfsLogTrace1
0x180005263  call    cs:__imp_RpcRevertToSelf
0x18000526a  nop     dword ptr [rax+rax+00h]
0x18000526f  jmp     short loc_1800052A0
0x180005271  mov     ebx, 80070005h
0x180005276  jmp     short loc_180005283
0x180005278  jle     short loc_180005283
0x18000527a  movzx   ebx, ax
0x18000527d  or      ebx, 80070000h
0x180005283  mov     [rsp+38h+var_18], 0FB3h
0x18000528b  mov     r9d, 6
0x180005291  lea     rdx, EFS_API_ERROR
0x180005298  mov     r8d, ebx
0x18000529b  call    fnEfsLogTrace1
0x1800052a0  mov     eax, ebx
0x1800052a2  add     rsp, 30h
0x1800052a6  pop     rbx
0x1800052a7  retn
```

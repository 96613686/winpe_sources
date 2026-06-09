# EdpRpcServiceFileEncryptionQueue

- ea: `0x180005550`
- end: `0x180005636`
- name: `EdpRpcServiceFileEncryptionQueue`
- size: `230`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1800037b8`
- `0x180005550`
- `0x18000bf0c`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000559d`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000559d`
- `EFSCORE!EfsDllDisabled` at `0x18000557b`
- `EFSCORE!EfsDllDisabled` at `0x18000557b`
- `EFSCORE!EdpDllServiceFileEncryptionQueue` at `0x1800055da`
- `EFSCORE!EdpDllServiceFileEncryptionQueue` at `0x1800055da`

## pseudocode

```c
__int64 __fastcall EdpRpcServiceFileEncryptionQueue(RPC_BINDING_HANDLE BindingHandle, char a2)
{
  int v4; // ebx
  RPC_STATUS IsClientLocal; // eax
  __int64 v6; // rcx
  int v7; // eax
  signed int v8; // eax
  __int64 v9; // rcx
  char v11; // [rsp+20h] [rbp-18h]
  unsigned int ClientLocalFlag; // [rsp+50h] [rbp+18h] BYREF

  ClientLocalFlag = 0;
  if ( !EfsServerInitialized )
    return (unsigned int)-2147024846;
  if ( (unsigned __int8)EfsDllDisabled() )
    return (unsigned int)-2147018881;
  IsClientLocal = I_RpcBindingIsClientLocal(BindingHandle, &ClientLocalFlag);
  v4 = IsClientLocal;
  if ( IsClientLocal )
  {
    if ( IsClientLocal > 0 )
      v4 = (unsigned __int16)IsClientLocal | 0x80070000;
    goto LABEL_16;
  }
  if ( !ClientLocalFlag )
  {
    v4 = -2147024891;
LABEL_16:
    v11 = 32;
    goto LABEL_17;
  }
  v7 = EfsEnforceClientAuthentication();
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
  if ( v4 < 0 )
  {
    v11 = 37;
LABEL_17:
    fnEfsLogTrace1(v6, (__int64)EFS_API_ERROR, v4, 6, v11);
    return (unsigned int)v4;
  }
  LOBYTE(v6) = a2;
  v8 = EdpDllServiceFileEncryptionQueue(v6);
  v4 = v8;
  if ( v8 < 0 )
    fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, v8, 6, 44);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180005550  mov     [rsp+arg_0], rbx
0x180005555  push    rdi
0x180005556  sub     rsp, 30h
0x18000555a  cmp     cs:EfsServerInitialized, 0
0x180005561  mov     dil, dl
0x180005564  mov     rbx, rcx
0x180005567  mov     [rsp+38h+ClientLocalFlag], 0
0x18000556f  jnz     short loc_18000557B
0x180005571  mov     ebx, 80070032h
0x180005576  jmp     loc_180005628
0x18000557b  call    cs:__imp_EfsDllDisabled
0x180005582  nop     dword ptr [rax+rax+00h]
0x180005587  test    al, al
0x180005589  jz      short loc_180005595
0x18000558b  mov     ebx, 8007177Fh
0x180005590  jmp     loc_180005628
0x180005595  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x18000559a  mov     rcx, rbx; BindingHandle
0x18000559d  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800055a4  nop     dword ptr [rax+rax+00h]
0x1800055a9  mov     ebx, eax
0x1800055ab  test    eax, eax
0x1800055ad  jnz     short loc_180005600
0x1800055af  cmp     [rsp+38h+ClientLocalFlag], eax
0x1800055b3  jz      short loc_1800055F9
0x1800055b5  call    EfsEnforceClientAuthentication
0x1800055ba  mov     ebx, eax
0x1800055bc  test    eax, eax
0x1800055be  jle     short loc_1800055C9
0x1800055c0  movzx   ebx, ax
0x1800055c3  or      ebx, 80070000h
0x1800055c9  test    ebx, ebx
0x1800055cb  jns     short loc_1800055D7
0x1800055cd  mov     dword ptr [rsp+38h+var_18], 0F25h
0x1800055d5  jmp     short loc_180005613
0x1800055d7  mov     cl, dil
0x1800055da  call    cs:__imp_EdpDllServiceFileEncryptionQueue
0x1800055e1  nop     dword ptr [rax+rax+00h]
0x1800055e6  mov     ebx, eax
0x1800055e8  test    eax, eax
0x1800055ea  jns     short loc_180005628
0x1800055ec  mov     dword ptr [rsp+38h+var_18], 0F2Ch
0x1800055f4  mov     r8d, eax
0x1800055f7  jmp     short loc_180005616
0x1800055f9  mov     ebx, 80070005h
0x1800055fe  jmp     short loc_18000560B
0x180005600  jle     short loc_18000560B
0x180005602  movzx   ebx, ax
0x180005605  or      ebx, 80070000h
0x18000560b  mov     dword ptr [rsp+38h+var_18], 0F20h
0x180005613  mov     r8d, ebx
0x180005616  mov     r9d, 6
0x18000561c  lea     rdx, EFS_API_ERROR
0x180005623  call    fnEfsLogTrace1
0x180005628  mov     eax, ebx
0x18000562a  mov     rbx, [rsp+38h+arg_0]
0x18000562f  add     rsp, 30h
0x180005633  pop     rdi
0x180005634  retn
```

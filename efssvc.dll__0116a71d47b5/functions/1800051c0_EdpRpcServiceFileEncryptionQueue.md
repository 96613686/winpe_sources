# EdpRpcServiceFileEncryptionQueue

- ea: `0x1800051c0`
- end: `0x180005293`
- name: `EdpRpcServiceFileEncryptionQueue`
- size: `211`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180003604`
- `0x1800051c0`
- `0x18000b308`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180005207`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180005207`
- `EFSCORE!EfsDllDisabled` at `0x1800051eb`
- `EFSCORE!EfsDllDisabled` at `0x1800051eb`
- `EFSCORE!EdpDllServiceFileEncryptionQueue` at `0x18000523e`
- `EFSCORE!EdpDllServiceFileEncryptionQueue` at `0x18000523e`

## pseudocode

```c
__int64 __fastcall EdpRpcServiceFileEncryptionQueue(RPC_BINDING_HANDLE BindingHandle, char a2)
{
  unsigned int v4; // ebx
  RPC_STATUS IsClientLocal; // eax
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  int v9; // ecx
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
  if ( (v4 & 0x80000000) != 0 )
  {
    v11 = 37;
LABEL_17:
    fnEfsLogTrace1(v6, (unsigned int)EFS_API_ERROR, v4, 6, v11);
    return v4;
  }
  LOBYTE(v6) = a2;
  v8 = EdpDllServiceFileEncryptionQueue(v6);
  v4 = v8;
  if ( v8 < 0 )
    fnEfsLogTrace1(v9, (unsigned int)EFS_API_ERROR, v8, 6, 44);
  return v4;
}

```

## disassembly

```asm
0x1800051c0  mov     [rsp+arg_0], rbx
0x1800051c5  push    rdi
0x1800051c6  sub     rsp, 30h
0x1800051ca  cmp     cs:EfsServerInitialized, 0
0x1800051d1  mov     dil, dl
0x1800051d4  mov     rbx, rcx
0x1800051d7  mov     [rsp+38h+ClientLocalFlag], 0
0x1800051df  jnz     short loc_1800051EB
0x1800051e1  mov     ebx, 80070032h
0x1800051e6  jmp     loc_180005286
0x1800051eb  call    cs:__imp_EfsDllDisabled
0x1800051f1  test    al, al
0x1800051f3  jz      short loc_1800051FF
0x1800051f5  mov     ebx, 8007177Fh
0x1800051fa  jmp     loc_180005286
0x1800051ff  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x180005204  mov     rcx, rbx; BindingHandle
0x180005207  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000520d  mov     ebx, eax
0x18000520f  test    eax, eax
0x180005211  jnz     short loc_18000525E
0x180005213  cmp     [rsp+38h+ClientLocalFlag], eax
0x180005217  jz      short loc_180005257
0x180005219  call    EfsEnforceClientAuthentication
0x18000521e  mov     ebx, eax
0x180005220  test    eax, eax
0x180005222  jle     short loc_18000522D
0x180005224  movzx   ebx, ax
0x180005227  or      ebx, 80070000h
0x18000522d  test    ebx, ebx
0x18000522f  jns     short loc_18000523B
0x180005231  mov     dword ptr [rsp+38h+var_18], 0F25h
0x180005239  jmp     short loc_180005271
0x18000523b  mov     cl, dil
0x18000523e  call    cs:__imp_EdpDllServiceFileEncryptionQueue
0x180005244  mov     ebx, eax
0x180005246  test    eax, eax
0x180005248  jns     short loc_180005286
0x18000524a  mov     dword ptr [rsp+38h+var_18], 0F2Ch
0x180005252  mov     r8d, eax
0x180005255  jmp     short loc_180005274
0x180005257  mov     ebx, 80070005h
0x18000525c  jmp     short loc_180005269
0x18000525e  jle     short loc_180005269
0x180005260  movzx   ebx, ax
0x180005263  or      ebx, 80070000h
0x180005269  mov     dword ptr [rsp+38h+var_18], 0F20h
0x180005271  mov     r8d, ebx
0x180005274  mov     r9d, 6
0x18000527a  lea     rdx, EFS_API_ERROR
0x180005281  call    fnEfsLogTrace1
0x180005286  mov     eax, ebx
0x180005288  mov     rbx, [rsp+38h+arg_0]
0x18000528d  add     rsp, 30h
0x180005291  pop     rdi
0x180005292  retn
```

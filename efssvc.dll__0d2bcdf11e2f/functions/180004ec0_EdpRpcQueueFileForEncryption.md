# EdpRpcQueueFileForEncryption

- ea: `0x180004ec0`
- end: `0x180005179`
- name: `EdpRpcQueueFileForEncryption`
- size: `697`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800037b8`
- `0x180004ec0`
- `0x18000bf0c`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000507e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000507e`
- `RPCRT4!RpcRevertToSelf` at `0x1800050b4`
- `RPCRT4!RpcRevertToSelf` at `0x180005125`
- `RPCRT4!RpcRevertToSelf` at `0x1800050b4`
- `RPCRT4!RpcRevertToSelf` at `0x180005125`
- `RPCRT4!RpcImpersonateClient` at `0x180004f9a`
- `RPCRT4!RpcImpersonateClient` at `0x180004f9a`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004f53`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004f53`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004fcd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004fcd`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005105`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005105`
- `EFSCORE!EdpDllQueueFileForEncryption` at `0x1800050d2`
- `EFSCORE!EdpDllQueueFileForEncryption` at `0x1800050d2`
- `EFSCORE!EfsDllDisabled` at `0x180004f0c`
- `EFSCORE!EfsDllDisabled` at `0x180004f0c`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005115`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005115`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005034`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005034`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000506b`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000506b`

## pseudocode

```c
__int64 __fastcall EdpRpcQueueFileForEncryption(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v5; // esi
  unsigned int v9; // ebx
  bool v10; // zf
  RPC_STATUS IsClientLocal; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  RPC_STATUS v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  signed int LastError; // eax
  __int64 v19; // rcx
  signed int v20; // eax
  signed int v21; // eax
  __int64 v22; // rcx
  signed int v23; // eax
  __int64 v24; // rcx
  char v26; // [rsp+20h] [rbp-81h]
  unsigned int ClientLocalFlag; // [rsp+30h] [rbp-71h] BYREF
  WINBOOL IsMember[3]; // [rsp+34h] [rbp-6Dh] BYREF
  _BYTE v29[24]; // [rsp+40h] [rbp-61h] BYREF
  __int64 v30; // [rsp+58h] [rbp-49h]

  v5 = 0;
  ClientLocalFlag = 0;
  IsMember[0] = 0;
  memset_0(v29, 0, 0x70u);
  if ( !EfsServerInitialized )
    return (unsigned int)-2147024846;
  if ( (unsigned __int8)EfsDllDisabled() )
    return (unsigned int)-2147018881;
  if ( a2 )
  {
    v10 = a3 == 0;
  }
  else
  {
    if ( a3 )
      return (unsigned int)-2147024809;
    v10 = a4 == 0;
  }
  if ( v10 || !a5 )
    return (unsigned int)-2147024809;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  v9 = IsClientLocal;
  if ( IsClientLocal )
  {
    if ( IsClientLocal > 0 )
      v9 = (unsigned __int16)IsClientLocal | 0x80070000;
    goto LABEL_46;
  }
  if ( !ClientLocalFlag )
  {
    v9 = -2147024891;
LABEL_46:
    fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v9, 6, 145);
    return v9;
  }
  v13 = EfsEnforceClientAuthentication();
  v9 = v13;
  if ( v13 > 0 )
    v9 = (unsigned __int16)v13 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    fnEfsLogTrace1(v14, (__int64)EFS_API_ERROR, v9, 6, 150);
    return v9;
  }
  v15 = RpcImpersonateClient(0);
  v9 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
    fnEfsLogTrace1(v16, (__int64)EFS_API_ERROR, v9, 6, 164);
    return v9;
  }
  if ( !CheckTokenMembership(0, g_AdminSid, IsMember) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v26 = -74;
LABEL_26:
    fnEfsLogTrace1(v19, (__int64)EFS_API_ERROR, v9, 6, v26);
    goto LABEL_42;
  }
  if ( !IsMember[0] )
  {
    v9 = -2147024891;
    fnEfsLogTrace1(v17, (__int64)EFS_API_ERROR, 0x80070005, 6, 189);
LABEL_42:
    RpcRevertToSelf();
    return v9;
  }
  if ( !(unsigned __int8)EfsDllGetUserInfo(v29) )
  {
    v20 = GetLastError();
    v9 = v20;
    if ( v20 > 0 )
      v9 = (unsigned __int16)v20 | 0x80070000;
    v26 = -61;
    goto LABEL_26;
  }
  if ( (unsigned int)EfsDllLoadUserProfile(v29, 0) )
  {
    RpcRevertToSelf();
    v23 = EdpDllQueueFileForEncryption(v30, a2, a3, a4, a5);
    v9 = v23;
    if ( v23 < 0 )
      fnEfsLogTrace1(v24, (__int64)EFS_API_ERROR, v23, 6, 219);
    EfsDllUnloadUserProfile(v29);
  }
  else
  {
    v5 = 1;
    v21 = GetLastError();
    v9 = v21;
    if ( v21 > 0 )
      v9 = (unsigned __int16)v21 | 0x80070000;
    fnEfsLogTrace1(v22, (__int64)EFS_API_ERROR, v9, 6, 203);
  }
  EfsDllFreeUserInfo(v29);
  if ( v5 )
    goto LABEL_42;
  return v9;
}

```

## disassembly

```asm
0x180004ec0  push    rbp
0x180004ec2  push    rbx
0x180004ec3  push    rsi
0x180004ec4  push    rdi
0x180004ec5  push    r12
0x180004ec7  push    r13
0x180004ec9  push    r14
0x180004ecb  push    r15
0x180004ecd  lea     rbp, [rsp-17h]
0x180004ed2  sub     rsp, 0B8h
0x180004ed9  xor     esi, esi
0x180004edb  lea     rcx, [rbp+4Fh+var_B0]; void *
0x180004edf  mov     r14, r8
0x180004ee2  mov     [rbp+4Fh+ClientLocalFlag], esi
0x180004ee5  mov     r13, rdx
0x180004ee8  mov     [rbp+4Fh+IsMember], esi
0x180004eeb  xor     edx, edx; Val
0x180004eed  mov     r12, r9
0x180004ef0  lea     r8d, [rsi+70h]; Size
0x180004ef4  call    memset_0
0x180004ef9  cmp     cs:EfsServerInitialized, sil
0x180004f00  jnz     short loc_180004F0C
0x180004f02  mov     ebx, 80070032h
0x180004f07  jmp     loc_180005162
0x180004f0c  call    cs:__imp_EfsDllDisabled
0x180004f13  nop     dword ptr [rax+rax+00h]
0x180004f18  test    al, al
0x180004f1a  jz      short loc_180004F26
0x180004f1c  mov     ebx, 8007177Fh
0x180004f21  jmp     loc_180005162
0x180004f26  test    r13, r13
0x180004f29  jnz     short loc_180004F3F
0x180004f2b  test    r14, r14
0x180004f2e  jnz     short loc_180004F35
0x180004f30  test    r12, r12
0x180004f33  jnz     short loc_180004F44
0x180004f35  mov     ebx, 80070057h
0x180004f3a  jmp     loc_180005162
0x180004f3f  test    r14, r14
0x180004f42  jmp     short loc_180004F33
0x180004f44  mov     r15, [rbp+4Fh+arg_20]
0x180004f48  test    r15, r15
0x180004f4b  jz      short loc_180004F35
0x180004f4d  lea     rdx, [rbp+4Fh+ClientLocalFlag]; ClientLocalFlag
0x180004f51  xor     ecx, ecx; BindingHandle
0x180004f53  call    cs:__imp_I_RpcBindingIsClientLocal
0x180004f5a  nop     dword ptr [rax+rax+00h]
0x180004f5f  mov     ebx, eax
0x180004f61  test    eax, eax
0x180004f63  jnz     loc_18000513A
0x180004f69  cmp     [rbp+4Fh+ClientLocalFlag], esi
0x180004f6c  jz      loc_180005133
0x180004f72  call    EfsEnforceClientAuthentication
0x180004f77  mov     ebx, eax
0x180004f79  mov     edi, 80070000h
0x180004f7e  test    eax, eax
0x180004f80  jle     short loc_180004F87
0x180004f82  movzx   ebx, ax
0x180004f85  or      ebx, edi
0x180004f87  test    ebx, ebx
0x180004f89  jns     short loc_180004F98
0x180004f8b  mov     dword ptr [rsp+0F0h+var_D0], 0E96h
0x180004f93  jmp     loc_18000514D
0x180004f98  xor     ecx, ecx; BindingHandle
0x180004f9a  call    cs:__imp_RpcImpersonateClient
0x180004fa1  nop     dword ptr [rax+rax+00h]
0x180004fa6  mov     ebx, eax
0x180004fa8  test    eax, eax
0x180004faa  jz      short loc_180004FC0
0x180004fac  jle     short loc_180004FB3
0x180004fae  movzx   ebx, ax
0x180004fb1  or      ebx, edi
0x180004fb3  mov     dword ptr [rsp+0F0h+var_D0], 0EA4h
0x180004fbb  jmp     loc_18000514D
0x180004fc0  mov     rdx, cs:g_AdminSid; SidToCheck
0x180004fc7  lea     r8, [rbp+4Fh+IsMember]; IsMember
0x180004fcb  xor     ecx, ecx; TokenHandle
0x180004fcd  call    cs:__imp_CheckTokenMembership
0x180004fd4  nop     dword ptr [rax+rax+00h]
0x180004fd9  test    eax, eax
0x180004fdb  jnz     short loc_180005016
0x180004fdd  call    cs:__imp_GetLastError
0x180004fe4  nop     dword ptr [rax+rax+00h]
0x180004fe9  mov     ebx, eax
0x180004feb  test    eax, eax
0x180004fed  jle     short loc_180004FF4
0x180004fef  movzx   ebx, ax
0x180004ff2  or      ebx, edi
0x180004ff4  mov     dword ptr [rsp+0F0h+var_D0], 0EB6h
0x180004ffc  mov     r8d, ebx
0x180004fff  mov     r9d, 6
0x180005005  lea     rdx, EFS_API_ERROR
0x18000500c  call    fnEfsLogTrace1
0x180005011  jmp     loc_180005125
0x180005016  cmp     [rbp+4Fh+IsMember], esi
0x180005019  jnz     short loc_180005030
0x18000501b  mov     ebx, 80070005h
0x180005020  mov     dword ptr [rsp+0F0h+var_D0], 0EBDh
0x180005028  mov     r8d, 80070005h
0x18000502e  jmp     short loc_180004FFF
0x180005030  lea     rcx, [rbp+4Fh+var_B0]
0x180005034  call    cs:__imp_EfsDllGetUserInfo
0x18000503b  nop     dword ptr [rax+rax+00h]
0x180005040  test    al, al
0x180005042  jnz     short loc_180005065
0x180005044  call    cs:__imp_GetLastError
0x18000504b  nop     dword ptr [rax+rax+00h]
0x180005050  mov     ebx, eax
0x180005052  test    eax, eax
0x180005054  jle     short loc_18000505B
0x180005056  movzx   ebx, ax
0x180005059  or      ebx, edi
0x18000505b  mov     dword ptr [rsp+0F0h+var_D0], 0EC3h
0x180005063  jmp     short loc_180004FFC
0x180005065  xor     edx, edx
0x180005067  lea     rcx, [rbp+4Fh+var_B0]
0x18000506b  call    cs:__imp_EfsDllLoadUserProfile
0x180005072  nop     dword ptr [rax+rax+00h]
0x180005077  test    eax, eax
0x180005079  jnz     short loc_1800050B4
0x18000507b  lea     esi, [rax+1]
0x18000507e  call    cs:__imp_GetLastError
0x180005085  nop     dword ptr [rax+rax+00h]
0x18000508a  mov     ebx, eax
0x18000508c  test    eax, eax
0x18000508e  jle     short loc_180005095
0x180005090  movzx   ebx, ax
0x180005093  or      ebx, edi
0x180005095  mov     r9d, 6
0x18000509b  mov     dword ptr [rsp+0F0h+var_D0], 0ECBh
0x1800050a3  mov     r8d, ebx
0x1800050a6  lea     rdx, EFS_API_ERROR
0x1800050ad  call    fnEfsLogTrace1
0x1800050b2  jmp     short loc_180005111
0x1800050b4  call    cs:__imp_RpcRevertToSelf
0x1800050bb  nop     dword ptr [rax+rax+00h]
0x1800050c0  mov     rcx, [rbp+4Fh+var_98]
0x1800050c4  mov     r9, r12
0x1800050c7  mov     r8, r14
0x1800050ca  mov     qword ptr [rsp+0F0h+var_D0], r15
0x1800050cf  mov     rdx, r13
0x1800050d2  call    cs:__imp_EdpDllQueueFileForEncryption
0x1800050d9  nop     dword ptr [rax+rax+00h]
0x1800050de  mov     ebx, eax
0x1800050e0  test    eax, eax
0x1800050e2  jns     short loc_180005101
0x1800050e4  mov     r9d, 6
0x1800050ea  mov     dword ptr [rsp+0F0h+var_D0], 0EDBh
0x1800050f2  mov     r8d, eax
0x1800050f5  lea     rdx, EFS_API_ERROR
0x1800050fc  call    fnEfsLogTrace1
0x180005101  lea     rcx, [rbp+4Fh+var_B0]
0x180005105  call    cs:__imp_EfsDllUnloadUserProfile
0x18000510c  nop     dword ptr [rax+rax+00h]
0x180005111  lea     rcx, [rbp+4Fh+var_B0]
0x180005115  call    cs:__imp_EfsDllFreeUserInfo
0x18000511c  nop     dword ptr [rax+rax+00h]
0x180005121  test    esi, esi
0x180005123  jz      short loc_180005162
0x180005125  call    cs:__imp_RpcRevertToSelf
0x18000512c  nop     dword ptr [rax+rax+00h]
0x180005131  jmp     short loc_180005162
0x180005133  mov     ebx, 80070005h
0x180005138  jmp     short loc_180005145
0x18000513a  jle     short loc_180005145
0x18000513c  movzx   ebx, ax
0x18000513f  or      ebx, 80070000h
0x180005145  mov     dword ptr [rsp+0F0h+var_D0], 0E91h
0x18000514d  mov     r9d, 6
0x180005153  lea     rdx, EFS_API_ERROR
0x18000515a  mov     r8d, ebx
0x18000515d  call    fnEfsLogTrace1
0x180005162  mov     eax, ebx
0x180005164  add     rsp, 0B8h
0x18000516b  pop     r15
0x18000516d  pop     r14
0x18000516f  pop     r13
0x180005171  pop     r12
0x180005173  pop     rdi
0x180005174  pop     rsi
0x180005175  pop     rbx
0x180005176  pop     rbp
0x180005177  retn
```

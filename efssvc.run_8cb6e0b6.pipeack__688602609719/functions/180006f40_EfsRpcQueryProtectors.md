# EfsRpcQueryProtectors

- ea: `0x180006f40`
- end: `0x1800070bd`
- name: `EfsRpcQueryProtectors`
- size: `381`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800036a0`
- `0x1800036e0`
- `0x1800037b8`
- `0x180006f40`
- `0x18000bf0c`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180007081`
- `RPCRT4!RpcRevertToSelf` at `0x180007081`
- `RPCRT4!RpcImpersonateClient` at `0x180007023`
- `RPCRT4!RpcImpersonateClient` at `0x180007023`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006fab`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006fab`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180007005`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180007005`
- `EFSCORE!EfsDllDisabled` at `0x180006f7c`
- `EFSCORE!EfsDllDisabled` at `0x180006f7c`
- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x180007062`
- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x180007062`
- `EFSCORE!EfsDllFreeHeap` at `0x18000709e`
- `EFSCORE!EfsDllFreeHeap` at `0x18000709e`

## pseudocode

```c
__int64 __fastcall EfsRpcQueryProtectors(RPC_BINDING_HANDLE BindingHandle, __int64 a2, _QWORD *a3)
{
  unsigned int ProtectorsSrv; // ebx
  unsigned int v7; // eax
  int v8; // ecx
  unsigned int LocalFileName; // eax
  int v10; // ecx
  RPC_STATUS v11; // eax
  int v12; // ecx
  char *v13; // rax
  void *v14; // rdi
  unsigned int ClientLocalFlag; // [rsp+30h] [rbp-18h] BYREF
  __int64 v17; // [rsp+38h] [rbp-10h] BYREF
  __int16 v18; // [rsp+68h] [rbp+20h] BYREF

  v17 = 0;
  v18 = 0;
  ClientLocalFlag = 0;
  if ( EfsServerInitialized )
  {
    if ( (unsigned __int8)EfsDllDisabled(BindingHandle) )
    {
      ProtectorsSrv = 6015;
    }
    else if ( a3 )
    {
      if ( I_RpcBindingIsClientLocal(BindingHandle, &ClientLocalFlag) || !ClientLocalFlag )
      {
        ProtectorsSrv = 50;
      }
      else
      {
        v7 = EfsEnforceClientAuthentication();
        ProtectorsSrv = v7;
        if ( v7 )
        {
          fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v7, 6, 123);
        }
        else
        {
          LocalFileName = EfsDllGetLocalFileName(a2, 0, &v17, &v18);
          ProtectorsSrv = LocalFileName;
          if ( LocalFileName )
          {
            fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 128);
          }
          else
          {
            v11 = RpcImpersonateClient(0);
            ProtectorsSrv = v11;
            if ( v11 )
            {
              fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v11, 6, 133);
            }
            else
            {
              v13 = (char *)MIDL_user_allocate(0x10u);
              v14 = v13;
              if ( v13 )
              {
                ProtectorsSrv = EfsDllQueryProtectorsSrv(v17, v13, v13 + 8);
                if ( ProtectorsSrv )
                  MIDL_user_free(v14);
                else
                  *a3 = v14;
              }
              else
              {
                ProtectorsSrv = 8;
              }
              RpcRevertToSelf();
            }
          }
        }
      }
    }
    else
    {
      ProtectorsSrv = 87;
    }
    if ( v17 )
      EfsDllFreeHeap(v17);
  }
  else
  {
    return 50;
  }
  return ProtectorsSrv;
}

```

## disassembly

```asm
0x180006f40  mov     [rsp+arg_0], rbx
0x180006f45  mov     [rsp+arg_8], rsi
0x180006f4a  push    rdi
0x180006f4b  sub     rsp, 40h
0x180006f4f  xor     eax, eax
0x180006f51  mov     [rsp+48h+var_10], 0
0x180006f5a  cmp     cs:EfsServerInitialized, al
0x180006f60  mov     rsi, r8
0x180006f63  mov     rdi, rdx
0x180006f66  mov     [rsp+48h+arg_18], ax
0x180006f6b  mov     rbx, rcx
0x180006f6e  mov     [rsp+48h+ClientLocalFlag], eax
0x180006f72  jnz     short loc_180006F7C
0x180006f74  lea     ebx, [rax+32h]
0x180006f77  jmp     loc_1800070AA
0x180006f7c  call    cs:__imp_EfsDllDisabled
0x180006f83  nop     dword ptr [rax+rax+00h]
0x180006f88  test    al, al
0x180006f8a  jz      short loc_180006F96
0x180006f8c  mov     ebx, 177Fh
0x180006f91  jmp     loc_180007094
0x180006f96  test    rsi, rsi
0x180006f99  jnz     short loc_180006FA3
0x180006f9b  lea     ebx, [rsi+57h]
0x180006f9e  jmp     loc_180007094
0x180006fa3  lea     rdx, [rsp+48h+ClientLocalFlag]; ClientLocalFlag
0x180006fa8  mov     rcx, rbx; BindingHandle
0x180006fab  call    cs:__imp_I_RpcBindingIsClientLocal
0x180006fb2  nop     dword ptr [rax+rax+00h]
0x180006fb7  test    eax, eax
0x180006fb9  jnz     loc_18000708F
0x180006fbf  cmp     [rsp+48h+ClientLocalFlag], eax
0x180006fc3  jz      loc_18000708F
0x180006fc9  call    EfsEnforceClientAuthentication
0x180006fce  mov     ebx, eax
0x180006fd0  test    eax, eax
0x180006fd2  jz      short loc_180006FF6
0x180006fd4  mov     [rsp+48h+var_28], 57Bh
0x180006fdc  mov     r9d, 6
0x180006fe2  lea     rdx, EFS_API_ERROR
0x180006fe9  mov     r8d, eax
0x180006fec  call    fnEfsLogTrace1
0x180006ff1  jmp     loc_180007094
0x180006ff6  lea     r9, [rsp+48h+arg_18]
0x180006ffb  xor     edx, edx
0x180006ffd  lea     r8, [rsp+48h+var_10]
0x180007002  mov     rcx, rdi
0x180007005  call    cs:__imp_EfsDllGetLocalFileName
0x18000700c  nop     dword ptr [rax+rax+00h]
0x180007011  mov     ebx, eax
0x180007013  test    eax, eax
0x180007015  jz      short loc_180007021
0x180007017  mov     [rsp+48h+var_28], 580h
0x18000701f  jmp     short loc_180006FDC
0x180007021  xor     ecx, ecx; BindingHandle
0x180007023  call    cs:__imp_RpcImpersonateClient
0x18000702a  nop     dword ptr [rax+rax+00h]
0x18000702f  mov     ebx, eax
0x180007031  test    eax, eax
0x180007033  jz      short loc_18000703F
0x180007035  mov     [rsp+48h+var_28], 585h
0x18000703d  jmp     short loc_180006FDC
0x18000703f  mov     ecx, 10h; size
0x180007044  call    MIDL_user_allocate
0x180007049  mov     rdi, rax
0x18000704c  test    rax, rax
0x18000704f  jnz     short loc_180007056
0x180007051  lea     ebx, [rax+8]
0x180007054  jmp     short loc_180007081
0x180007056  mov     rcx, [rsp+48h+var_10]
0x18000705b  lea     r8, [rax+8]
0x18000705f  mov     rdx, rdi
0x180007062  call    cs:__imp_EfsDllQueryProtectorsSrv
0x180007069  nop     dword ptr [rax+rax+00h]
0x18000706e  mov     ebx, eax
0x180007070  test    eax, eax
0x180007072  jnz     short loc_180007079
0x180007074  mov     [rsi], rdi
0x180007077  jmp     short loc_180007081
0x180007079  mov     rcx, rdi; void *
0x18000707c  call    MIDL_user_free
0x180007081  call    cs:__imp_RpcRevertToSelf
0x180007088  nop     dword ptr [rax+rax+00h]
0x18000708d  jmp     short loc_180007094
0x18000708f  mov     ebx, 32h ; '2'
0x180007094  mov     rcx, [rsp+48h+var_10]
0x180007099  test    rcx, rcx
0x18000709c  jz      short loc_1800070AA
0x18000709e  call    cs:__imp_EfsDllFreeHeap
0x1800070a5  nop     dword ptr [rax+rax+00h]
0x1800070aa  mov     rsi, [rsp+48h+arg_8]
0x1800070af  mov     eax, ebx
0x1800070b1  mov     rbx, [rsp+48h+arg_0]
0x1800070b6  add     rsp, 40h
0x1800070ba  pop     rdi
0x1800070bb  retn
```

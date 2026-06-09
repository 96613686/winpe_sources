# EfsRpcQueryProtectors

- ea: `0x1800068a0`
- end: `0x1800069f2`
- name: `EfsRpcQueryProtectors`
- size: `338`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003510`
- `0x180003540`
- `0x180003604`
- `0x1800068a0`
- `0x18000b308`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800069c3`
- `RPCRT4!RpcRevertToSelf` at `0x1800069c3`
- `RPCRT4!RpcImpersonateClient` at `0x180006971`
- `RPCRT4!RpcImpersonateClient` at `0x180006971`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006905`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180006905`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006959`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006959`
- `EFSCORE!EfsDllDisabled` at `0x1800068dc`
- `EFSCORE!EfsDllDisabled` at `0x1800068dc`
- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x1800069aa`
- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x1800069aa`
- `EFSCORE!EfsDllFreeHeap` at `0x1800069da`
- `EFSCORE!EfsDllFreeHeap` at `0x1800069da`

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
0x1800068a0  mov     [rsp+arg_0], rbx
0x1800068a5  mov     [rsp+arg_8], rsi
0x1800068aa  push    rdi
0x1800068ab  sub     rsp, 40h
0x1800068af  xor     eax, eax
0x1800068b1  mov     [rsp+48h+var_10], 0
0x1800068ba  cmp     cs:EfsServerInitialized, al
0x1800068c0  mov     rsi, r8
0x1800068c3  mov     rdi, rdx
0x1800068c6  mov     [rsp+48h+arg_18], ax
0x1800068cb  mov     rbx, rcx
0x1800068ce  mov     [rsp+48h+ClientLocalFlag], eax
0x1800068d2  jnz     short loc_1800068DC
0x1800068d4  lea     ebx, [rax+32h]
0x1800068d7  jmp     loc_1800069E0
0x1800068dc  call    cs:__imp_EfsDllDisabled
0x1800068e2  test    al, al
0x1800068e4  jz      short loc_1800068F0
0x1800068e6  mov     ebx, 177Fh
0x1800068eb  jmp     loc_1800069D0
0x1800068f0  test    rsi, rsi
0x1800068f3  jnz     short loc_1800068FD
0x1800068f5  lea     ebx, [rsi+57h]
0x1800068f8  jmp     loc_1800069D0
0x1800068fd  lea     rdx, [rsp+48h+ClientLocalFlag]; ClientLocalFlag
0x180006902  mov     rcx, rbx; BindingHandle
0x180006905  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000690b  test    eax, eax
0x18000690d  jnz     loc_1800069CB
0x180006913  cmp     [rsp+48h+ClientLocalFlag], eax
0x180006917  jz      loc_1800069CB
0x18000691d  call    EfsEnforceClientAuthentication
0x180006922  mov     ebx, eax
0x180006924  test    eax, eax
0x180006926  jz      short loc_18000694A
0x180006928  mov     [rsp+48h+var_28], 57Bh
0x180006930  mov     r9d, 6
0x180006936  lea     rdx, EFS_API_ERROR
0x18000693d  mov     r8d, eax
0x180006940  call    fnEfsLogTrace1
0x180006945  jmp     loc_1800069D0
0x18000694a  lea     r9, [rsp+48h+arg_18]
0x18000694f  xor     edx, edx
0x180006951  lea     r8, [rsp+48h+var_10]
0x180006956  mov     rcx, rdi
0x180006959  call    cs:__imp_EfsDllGetLocalFileName
0x18000695f  mov     ebx, eax
0x180006961  test    eax, eax
0x180006963  jz      short loc_18000696F
0x180006965  mov     [rsp+48h+var_28], 580h
0x18000696d  jmp     short loc_180006930
0x18000696f  xor     ecx, ecx; BindingHandle
0x180006971  call    cs:__imp_RpcImpersonateClient
0x180006977  mov     ebx, eax
0x180006979  test    eax, eax
0x18000697b  jz      short loc_180006987
0x18000697d  mov     [rsp+48h+var_28], 585h
0x180006985  jmp     short loc_180006930
0x180006987  mov     ecx, 10h; size
0x18000698c  call    MIDL_user_allocate
0x180006991  mov     rdi, rax
0x180006994  test    rax, rax
0x180006997  jnz     short loc_18000699E
0x180006999  lea     ebx, [rax+8]
0x18000699c  jmp     short loc_1800069C3
0x18000699e  mov     rcx, [rsp+48h+var_10]
0x1800069a3  lea     r8, [rax+8]
0x1800069a7  mov     rdx, rdi
0x1800069aa  call    cs:__imp_EfsDllQueryProtectorsSrv
0x1800069b0  mov     ebx, eax
0x1800069b2  test    eax, eax
0x1800069b4  jnz     short loc_1800069BB
0x1800069b6  mov     [rsi], rdi
0x1800069b9  jmp     short loc_1800069C3
0x1800069bb  mov     rcx, rdi; void *
0x1800069be  call    MIDL_user_free
0x1800069c3  call    cs:__imp_RpcRevertToSelf
0x1800069c9  jmp     short loc_1800069D0
0x1800069cb  mov     ebx, 32h ; '2'
0x1800069d0  mov     rcx, [rsp+48h+var_10]
0x1800069d5  test    rcx, rcx
0x1800069d8  jz      short loc_1800069E0
0x1800069da  call    cs:__imp_EfsDllFreeHeap
0x1800069e0  mov     rsi, [rsp+48h+arg_8]
0x1800069e5  mov     eax, ebx
0x1800069e7  mov     rbx, [rsp+48h+arg_0]
0x1800069ec  add     rsp, 40h
0x1800069f0  pop     rdi
0x1800069f1  retn
```

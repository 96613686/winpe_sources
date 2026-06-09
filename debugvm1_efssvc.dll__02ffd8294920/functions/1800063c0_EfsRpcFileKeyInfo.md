# EfsRpcFileKeyInfo

- ea: `0x1800063c0`
- end: `0x180006588`
- name: `EfsRpcFileKeyInfo`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003510`
- `0x180003540`
- `0x180003604`
- `0x1800063c0`
- `0x1800076b4`
- `0x180007ae8`
- `0x18000b308`
- `0x18000b480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064f3`
- `RPCRT4!RpcRevertToSelf` at `0x180006565`
- `RPCRT4!RpcRevertToSelf` at `0x180006565`
- `RPCRT4!RpcImpersonateClient` at `0x180006473`
- `RPCRT4!RpcImpersonateClient` at `0x180006473`
- `EFSCORE!EfsDllGetLocalFileName` at `0x18000645b`
- `EFSCORE!EfsDllGetLocalFileName` at `0x18000645b`
- `EFSCORE!EfsDllDisabled` at `0x1800063f7`
- `EFSCORE!EfsDllDisabled` at `0x1800063f7`
- `EFSCORE!EfsDllFileKeyInfoSrv` at `0x180006537`
- `EFSCORE!EfsDllFileKeyInfoSrv` at `0x180006537`
- `EFSCORE!EfsDllShareDecline` at `0x1800064e1`
- `EFSCORE!EfsDllShareDecline` at `0x1800064e1`
- `EFSCORE!EfsDllFreeHeap` at `0x180006575`
- `EFSCORE!EfsDllFreeHeap` at `0x180006575`

## pseudocode

```c
__int64 __fastcall EfsRpcFileKeyInfo(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  DWORD LastError; // ebx
  DWORD v9; // eax
  int v10; // ecx
  DWORD LocalFileName; // eax
  int v12; // ecx
  RPC_STATUS v13; // eax
  int v14; // ecx
  DWORD v15; // eax
  int v16; // ecx
  DWORD v17; // eax
  int v18; // ecx
  _QWORD *v19; // rax
  _QWORD *v20; // rdi
  void *v21; // rcx
  __int16 v23; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v24[6]; // [rsp+38h] [rbp-30h] BYREF

  v24[0] = 0;
  v23 = 0;
  if ( !EfsServerInitialized )
    return 50;
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    LastError = 6015;
    goto LABEL_32;
  }
  v9 = EfsEnforceClientAuthentication();
  LastError = v9;
  if ( !v9 )
  {
    if ( !a4 )
    {
      LastError = 87;
      goto LABEL_32;
    }
    *a4 = 0;
    LocalFileName = EfsDllGetLocalFileName(a2, 0, v24, &v23);
    LastError = LocalFileName;
    if ( LocalFileName )
    {
      fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 237);
      goto LABEL_32;
    }
    v13 = RpcImpersonateClient(0);
    LastError = v13;
    if ( v13 )
    {
      fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 6, 242);
      goto LABEL_32;
    }
    v15 = EfsEnsureLocalPath(v24[0]);
    LastError = v15;
    if ( v15 )
    {
      fnEfsLogTrace1(v16, (unsigned int)EFS_API_ERROR, v15, 6, 248);
      goto LABEL_31;
    }
    if ( (unsigned int)EfspCheckForNetSession() )
    {
      if ( v23 == 1 )
      {
        LastError = 5;
        goto LABEL_31;
      }
      if ( (unsigned int)EfsDllShareDecline(a2, 1, 128) )
      {
        LastError = GetLastError();
        v17 = GetLastError();
        fnEfsLogTrace1(v18, (unsigned int)EFS_API_ERROR, v17, 6, 9);
        goto LABEL_31;
      }
      LastError = EfspIsValidNetworkProtSeq(a1);
      if ( LastError )
        goto LABEL_31;
    }
    v19 = MIDL_user_allocate(0x10u);
    v20 = v19;
    if ( v19 )
    {
      LastError = EfsDllFileKeyInfoSrv(v24[0], a3, v19, v19 + 1);
      if ( LastError )
      {
        v21 = (void *)v20[1];
        if ( v21 )
          MIDL_user_free(v21);
      }
      else if ( v20[1] )
      {
        *a4 = v20;
        goto LABEL_31;
      }
      MIDL_user_free(v20);
      goto LABEL_31;
    }
    LastError = 8;
LABEL_31:
    RpcRevertToSelf();
    goto LABEL_32;
  }
  fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 227);
LABEL_32:
  if ( v24[0] )
    EfsDllFreeHeap();
  return LastError;
}

```

## disassembly

```asm
0x1800063c0  push    rbx
0x1800063c2  push    rbp
0x1800063c3  push    rsi
0x1800063c4  push    rdi
0x1800063c5  push    r14
0x1800063c7  sub     rsp, 40h
0x1800063cb  xor     eax, eax
0x1800063cd  mov     [rsp+68h+var_30], 0
0x1800063d6  cmp     cs:EfsServerInitialized, al
0x1800063dc  mov     rsi, r9
0x1800063df  mov     r14d, r8d
0x1800063e2  mov     [rsp+68h+var_38], ax
0x1800063e7  mov     rdi, rdx
0x1800063ea  mov     rbp, rcx
0x1800063ed  jnz     short loc_1800063F7
0x1800063ef  lea     ebx, [rax+32h]
0x1800063f2  jmp     loc_18000657B
0x1800063f7  call    cs:__imp_EfsDllDisabled
0x1800063fd  test    al, al
0x1800063ff  jz      short loc_18000640B
0x180006401  mov     ebx, 177Fh
0x180006406  jmp     loc_18000656B
0x18000640b  call    EfsEnforceClientAuthentication
0x180006410  mov     ebx, eax
0x180006412  test    eax, eax
0x180006414  jz      short loc_180006438
0x180006416  mov     [rsp+68h+var_48], 7E3h
0x18000641e  mov     r9d, 6
0x180006424  lea     rdx, EFS_API_ERROR
0x18000642b  mov     r8d, eax
0x18000642e  call    fnEfsLogTrace1
0x180006433  jmp     loc_18000656B
0x180006438  test    rsi, rsi
0x18000643b  jnz     short loc_180006445
0x18000643d  lea     ebx, [rsi+57h]
0x180006440  jmp     loc_18000656B
0x180006445  lea     r9, [rsp+68h+var_38]
0x18000644a  mov     qword ptr [rsi], 0
0x180006451  lea     r8, [rsp+68h+var_30]
0x180006456  xor     edx, edx
0x180006458  mov     rcx, rdi
0x18000645b  call    cs:__imp_EfsDllGetLocalFileName
0x180006461  mov     ebx, eax
0x180006463  test    eax, eax
0x180006465  jz      short loc_180006471
0x180006467  mov     [rsp+68h+var_48], 7EDh
0x18000646f  jmp     short loc_18000641E
0x180006471  xor     ecx, ecx; BindingHandle
0x180006473  call    cs:__imp_RpcImpersonateClient
0x180006479  mov     ebx, eax
0x18000647b  test    eax, eax
0x18000647d  jz      short loc_180006489
0x18000647f  mov     [rsp+68h+var_48], 7F2h
0x180006487  jmp     short loc_18000641E
0x180006489  mov     rcx, [rsp+68h+var_30]
0x18000648e  call    EfsEnsureLocalPath
0x180006493  mov     ebx, eax
0x180006495  test    eax, eax
0x180006497  jz      short loc_1800064BB
0x180006499  mov     [rsp+68h+var_48], 7F8h
0x1800064a1  mov     r8d, eax
0x1800064a4  lea     rdx, EFS_API_ERROR
0x1800064ab  mov     r9d, 6
0x1800064b1  call    fnEfsLogTrace1
0x1800064b6  jmp     loc_180006565
0x1800064bb  call    EfspCheckForNetSession
0x1800064c0  test    eax, eax
0x1800064c2  jz      short loc_180006511
0x1800064c4  mov     edx, 1
0x1800064c9  cmp     [rsp+68h+var_38], dx
0x1800064ce  jnz     short loc_1800064D8
0x1800064d0  lea     ebx, [rdx+4]
0x1800064d3  jmp     loc_180006565
0x1800064d8  mov     r8d, 80h
0x1800064de  mov     rcx, rdi
0x1800064e1  call    cs:__imp_EfsDllShareDecline
0x1800064e7  test    eax, eax
0x1800064e9  jz      short loc_180006503
0x1800064eb  call    cs:__imp_GetLastError
0x1800064f1  mov     ebx, eax
0x1800064f3  call    cs:__imp_GetLastError
0x1800064f9  mov     [rsp+68h+var_48], 809h
0x180006501  jmp     short loc_1800064A1
0x180006503  mov     rcx, rbp
0x180006506  call    EfspIsValidNetworkProtSeq
0x18000650b  mov     ebx, eax
0x18000650d  test    eax, eax
0x18000650f  jnz     short loc_180006565
0x180006511  mov     ecx, 10h; size
0x180006516  call    MIDL_user_allocate
0x18000651b  mov     rdi, rax
0x18000651e  test    rax, rax
0x180006521  jnz     short loc_180006528
0x180006523  lea     ebx, [rax+8]
0x180006526  jmp     short loc_180006565
0x180006528  mov     rcx, [rsp+68h+var_30]
0x18000652d  lea     r9, [rax+8]
0x180006531  mov     r8, rdi
0x180006534  mov     edx, r14d
0x180006537  call    cs:__imp_EfsDllFileKeyInfoSrv
0x18000653d  mov     ebx, eax
0x18000653f  test    eax, eax
0x180006541  jnz     short loc_18000654F
0x180006543  cmp     qword ptr [rdi+8], 0
0x180006548  jz      short loc_18000655D
0x18000654a  mov     [rsi], rdi
0x18000654d  jmp     short loc_180006565
0x18000654f  mov     rcx, [rdi+8]; void *
0x180006553  test    rcx, rcx
0x180006556  jz      short loc_18000655D
0x180006558  call    MIDL_user_free
0x18000655d  mov     rcx, rdi; void *
0x180006560  call    MIDL_user_free
0x180006565  call    cs:__imp_RpcRevertToSelf
0x18000656b  mov     rcx, [rsp+68h+var_30]
0x180006570  test    rcx, rcx
0x180006573  jz      short loc_18000657B
0x180006575  call    cs:__imp_EfsDllFreeHeap
0x18000657b  mov     eax, ebx
0x18000657d  add     rsp, 40h
0x180006581  pop     r14
0x180006583  pop     rdi
0x180006584  pop     rsi
0x180006585  pop     rbp
0x180006586  pop     rbx
0x180006587  retn
```

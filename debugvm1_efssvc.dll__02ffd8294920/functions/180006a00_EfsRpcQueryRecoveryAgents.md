# EfsRpcQueryRecoveryAgents

- ea: `0x180006a00`
- end: `0x180006b9f`
- name: `EfsRpcQueryRecoveryAgents`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x180003510`
- `0x180003540`
- `0x180003604`
- `0x180006a00`
- `0x1800076b4`
- `0x180007ae8`
- `0x18000b308`
- `0x18000b480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b23`
- `RPCRT4!RpcRevertToSelf` at `0x180006b7e`
- `RPCRT4!RpcRevertToSelf` at `0x180006b7e`
- `RPCRT4!RpcImpersonateClient` at `0x180006aab`
- `RPCRT4!RpcImpersonateClient` at `0x180006aab`
- `EFSCORE!EfsDllQueryRecoveryAgentsSrv` at `0x180006b5e`
- `EFSCORE!EfsDllQueryRecoveryAgentsSrv` at `0x180006b5e`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006a93`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006a93`
- `EFSCORE!EfsDllDisabled` at `0x180006a33`
- `EFSCORE!EfsDllDisabled` at `0x180006a33`
- `EFSCORE!EfsDllShareDecline` at `0x180006b19`
- `EFSCORE!EfsDllShareDecline` at `0x180006b19`
- `EFSCORE!EfsDllFreeHeap` at `0x180006b8e`
- `EFSCORE!EfsDllFreeHeap` at `0x180006b8e`

## pseudocode

```c
__int64 __fastcall EfsRpcQueryRecoveryAgents(__int64 a1, __int64 a2, _QWORD *a3)
{
  DWORD LastError; // ebx
  DWORD v7; // eax
  int v8; // ecx
  DWORD LocalFileName; // eax
  int v10; // ecx
  RPC_STATUS v11; // eax
  int v12; // ecx
  DWORD v13; // eax
  int v14; // ecx
  char *v15; // rax
  void *v16; // rdi
  _QWORD v18[7]; // [rsp+30h] [rbp-38h] BYREF
  __int16 v19; // [rsp+88h] [rbp+20h] BYREF

  v18[0] = 0;
  v19 = 0;
  if ( !EfsServerInitialized )
    return 50;
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    LastError = 6015;
    goto LABEL_28;
  }
  if ( !a3 )
  {
    LastError = 87;
    goto LABEL_28;
  }
  v7 = EfsEnforceClientAuthentication();
  LastError = v7;
  if ( !v7 )
  {
    LocalFileName = EfsDllGetLocalFileName(a2, 0, v18, &v19);
    LastError = LocalFileName;
    if ( LocalFileName )
    {
      fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 246);
      goto LABEL_28;
    }
    v11 = RpcImpersonateClient(0);
    LastError = v11;
    if ( v11 )
    {
      fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v11, 6, 251);
      goto LABEL_28;
    }
    v13 = EfsEnsureLocalPath(v18[0]);
    LastError = v13;
    if ( v13 )
    {
      fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 6, 1);
LABEL_27:
      RpcRevertToSelf();
      goto LABEL_28;
    }
    if ( (unsigned int)EfspCheckForNetSession() )
    {
      if ( v19 == 1 )
      {
        LastError = 5;
        goto LABEL_27;
      }
      if ( (unsigned int)EfsDllShareDecline(a2, 1, 128) )
      {
        LastError = GetLastError();
        goto LABEL_27;
      }
      LastError = EfspIsValidNetworkProtSeq(a1);
      if ( LastError )
        goto LABEL_27;
    }
    v15 = (char *)MIDL_user_allocate(0x10u);
    v16 = v15;
    if ( v15 )
    {
      LastError = EfsDllQueryRecoveryAgentsSrv(v18[0], v15, v15 + 8);
      if ( LastError )
      {
        MIDL_user_free(v16);
        *a3 = 0;
      }
      else
      {
        *a3 = v16;
      }
    }
    else
    {
      LastError = 8;
    }
    goto LABEL_27;
  }
  fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v7, 6, 241);
LABEL_28:
  if ( v18[0] )
    EfsDllFreeHeap();
  return LastError;
}

```

## disassembly

```asm
0x180006a00  mov     r11, rsp
0x180006a03  push    rbx
0x180006a04  push    rbp
0x180006a05  push    rsi
0x180006a06  push    rdi
0x180006a07  sub     rsp, 48h
0x180006a0b  xor     eax, eax
0x180006a0d  mov     qword ptr [r11-38h], 0
0x180006a15  cmp     cs:EfsServerInitialized, al
0x180006a1b  mov     rsi, r8
0x180006a1e  mov     rdi, rdx
0x180006a21  mov     [r11+20h], ax
0x180006a26  mov     rbp, rcx
0x180006a29  jnz     short loc_180006A33
0x180006a2b  lea     ebx, [rax+32h]
0x180006a2e  jmp     loc_180006B94
0x180006a33  call    cs:__imp_EfsDllDisabled
0x180006a39  test    al, al
0x180006a3b  jz      short loc_180006A47
0x180006a3d  mov     ebx, 177Fh
0x180006a42  jmp     loc_180006B84
0x180006a47  test    rsi, rsi
0x180006a4a  jnz     short loc_180006A54
0x180006a4c  lea     ebx, [rsi+57h]
0x180006a4f  jmp     loc_180006B84
0x180006a54  call    EfsEnforceClientAuthentication
0x180006a59  mov     ebx, eax
0x180006a5b  test    eax, eax
0x180006a5d  jz      short loc_180006A81
0x180006a5f  mov     [rsp+68h+var_48], 4F1h
0x180006a67  mov     r9d, 6
0x180006a6d  lea     rdx, EFS_API_ERROR
0x180006a74  mov     r8d, eax
0x180006a77  call    fnEfsLogTrace1
0x180006a7c  jmp     loc_180006B84
0x180006a81  lea     r9, [rsp+68h+arg_18]
0x180006a89  xor     edx, edx
0x180006a8b  lea     r8, [rsp+68h+var_38]
0x180006a90  mov     rcx, rdi
0x180006a93  call    cs:__imp_EfsDllGetLocalFileName
0x180006a99  mov     ebx, eax
0x180006a9b  test    eax, eax
0x180006a9d  jz      short loc_180006AA9
0x180006a9f  mov     [rsp+68h+var_48], 4F6h
0x180006aa7  jmp     short loc_180006A67
0x180006aa9  xor     ecx, ecx; BindingHandle
0x180006aab  call    cs:__imp_RpcImpersonateClient
0x180006ab1  mov     ebx, eax
0x180006ab3  test    eax, eax
0x180006ab5  jz      short loc_180006AC1
0x180006ab7  mov     [rsp+68h+var_48], 4FBh
0x180006abf  jmp     short loc_180006A67
0x180006ac1  mov     rcx, [rsp+68h+var_38]
0x180006ac6  call    EfsEnsureLocalPath
0x180006acb  mov     ebx, eax
0x180006acd  test    eax, eax
0x180006acf  jz      short loc_180006AF3
0x180006ad1  mov     r9d, 6
0x180006ad7  mov     [rsp+68h+var_48], 501h
0x180006adf  mov     r8d, eax
0x180006ae2  lea     rdx, EFS_API_ERROR
0x180006ae9  call    fnEfsLogTrace1
0x180006aee  jmp     loc_180006B7E
0x180006af3  call    EfspCheckForNetSession
0x180006af8  test    eax, eax
0x180006afa  jz      short loc_180006B3B
0x180006afc  mov     edx, 1
0x180006b01  cmp     [rsp+68h+arg_18], dx
0x180006b09  jnz     short loc_180006B10
0x180006b0b  lea     ebx, [rdx+4]
0x180006b0e  jmp     short loc_180006B7E
0x180006b10  mov     r8d, 80h
0x180006b16  mov     rcx, rdi
0x180006b19  call    cs:__imp_EfsDllShareDecline
0x180006b1f  test    eax, eax
0x180006b21  jz      short loc_180006B2D
0x180006b23  call    cs:__imp_GetLastError
0x180006b29  mov     ebx, eax
0x180006b2b  jmp     short loc_180006B7E
0x180006b2d  mov     rcx, rbp
0x180006b30  call    EfspIsValidNetworkProtSeq
0x180006b35  mov     ebx, eax
0x180006b37  test    eax, eax
0x180006b39  jnz     short loc_180006B7E
0x180006b3b  mov     ecx, 10h; size
0x180006b40  call    MIDL_user_allocate
0x180006b45  mov     rdi, rax
0x180006b48  test    rax, rax
0x180006b4b  jnz     short loc_180006B52
0x180006b4d  lea     ebx, [rax+8]
0x180006b50  jmp     short loc_180006B7E
0x180006b52  mov     rcx, [rsp+68h+var_38]
0x180006b57  lea     r8, [rax+8]
0x180006b5b  mov     rdx, rdi
0x180006b5e  call    cs:__imp_EfsDllQueryRecoveryAgentsSrv
0x180006b64  mov     ebx, eax
0x180006b66  test    eax, eax
0x180006b68  jnz     short loc_180006B6F
0x180006b6a  mov     [rsi], rdi
0x180006b6d  jmp     short loc_180006B7E
0x180006b6f  mov     rcx, rdi; void *
0x180006b72  call    MIDL_user_free
0x180006b77  mov     qword ptr [rsi], 0
0x180006b7e  call    cs:__imp_RpcRevertToSelf
0x180006b84  mov     rcx, [rsp+68h+var_38]
0x180006b89  test    rcx, rcx
0x180006b8c  jz      short loc_180006B94
0x180006b8e  call    cs:__imp_EfsDllFreeHeap
0x180006b94  mov     eax, ebx
0x180006b96  add     rsp, 48h
0x180006b9a  pop     rdi
0x180006b9b  pop     rsi
0x180006b9c  pop     rbp
0x180006b9d  pop     rbx
0x180006b9e  retn
```

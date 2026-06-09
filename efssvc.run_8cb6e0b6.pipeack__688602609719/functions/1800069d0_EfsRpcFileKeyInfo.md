# EfsRpcFileKeyInfo

- ea: `0x1800069d0`
- end: `0x180006bcf`
- name: `EfsRpcFileKeyInfo`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800036a0`
- `0x1800036e0`
- `0x1800037b8`
- `0x1800069d0`
- `0x180007f38`
- `0x180008404`
- `0x18000bf0c`
- `0x18000c094`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b21`
- `RPCRT4!RpcRevertToSelf` at `0x180006b9f`
- `RPCRT4!RpcRevertToSelf` at `0x180006b9f`
- `RPCRT4!RpcImpersonateClient` at `0x180006a8f`
- `RPCRT4!RpcImpersonateClient` at `0x180006a8f`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006a71`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006a71`
- `EFSCORE!EfsDllDisabled` at `0x180006a07`
- `EFSCORE!EfsDllDisabled` at `0x180006a07`
- `EFSCORE!EfsDllFileKeyInfoSrv` at `0x180006b6b`
- `EFSCORE!EfsDllFileKeyInfoSrv` at `0x180006b6b`
- `EFSCORE!EfsDllShareDecline` at `0x180006b03`
- `EFSCORE!EfsDllShareDecline` at `0x180006b03`
- `EFSCORE!EfsDllFreeHeap` at `0x180006bb5`
- `EFSCORE!EfsDllFreeHeap` at `0x180006bb5`

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
0x1800069d0  push    rbx
0x1800069d2  push    rbp
0x1800069d3  push    rsi
0x1800069d4  push    rdi
0x1800069d5  push    r14
0x1800069d7  sub     rsp, 40h
0x1800069db  xor     eax, eax
0x1800069dd  mov     [rsp+68h+var_30], 0
0x1800069e6  cmp     cs:EfsServerInitialized, al
0x1800069ec  mov     rsi, r9
0x1800069ef  mov     r14d, r8d
0x1800069f2  mov     [rsp+68h+var_38], ax
0x1800069f7  mov     rdi, rdx
0x1800069fa  mov     rbp, rcx
0x1800069fd  jnz     short loc_180006A07
0x1800069ff  lea     ebx, [rax+32h]
0x180006a02  jmp     loc_180006BC1
0x180006a07  call    cs:__imp_EfsDllDisabled
0x180006a0e  nop     dword ptr [rax+rax+00h]
0x180006a13  test    al, al
0x180006a15  jz      short loc_180006A21
0x180006a17  mov     ebx, 177Fh
0x180006a1c  jmp     loc_180006BAB
0x180006a21  call    EfsEnforceClientAuthentication
0x180006a26  mov     ebx, eax
0x180006a28  test    eax, eax
0x180006a2a  jz      short loc_180006A4E
0x180006a2c  mov     [rsp+68h+var_48], 7E3h
0x180006a34  mov     r9d, 6
0x180006a3a  lea     rdx, EFS_API_ERROR
0x180006a41  mov     r8d, eax
0x180006a44  call    fnEfsLogTrace1
0x180006a49  jmp     loc_180006BAB
0x180006a4e  test    rsi, rsi
0x180006a51  jnz     short loc_180006A5B
0x180006a53  lea     ebx, [rsi+57h]
0x180006a56  jmp     loc_180006BAB
0x180006a5b  lea     r9, [rsp+68h+var_38]
0x180006a60  mov     qword ptr [rsi], 0
0x180006a67  lea     r8, [rsp+68h+var_30]
0x180006a6c  xor     edx, edx
0x180006a6e  mov     rcx, rdi
0x180006a71  call    cs:__imp_EfsDllGetLocalFileName
0x180006a78  nop     dword ptr [rax+rax+00h]
0x180006a7d  mov     ebx, eax
0x180006a7f  test    eax, eax
0x180006a81  jz      short loc_180006A8D
0x180006a83  mov     [rsp+68h+var_48], 7EDh
0x180006a8b  jmp     short loc_180006A34
0x180006a8d  xor     ecx, ecx; BindingHandle
0x180006a8f  call    cs:__imp_RpcImpersonateClient
0x180006a96  nop     dword ptr [rax+rax+00h]
0x180006a9b  mov     ebx, eax
0x180006a9d  test    eax, eax
0x180006a9f  jz      short loc_180006AAB
0x180006aa1  mov     [rsp+68h+var_48], 7F2h
0x180006aa9  jmp     short loc_180006A34
0x180006aab  mov     rcx, [rsp+68h+var_30]
0x180006ab0  call    EfsEnsureLocalPath
0x180006ab5  mov     ebx, eax
0x180006ab7  test    eax, eax
0x180006ab9  jz      short loc_180006ADD
0x180006abb  mov     [rsp+68h+var_48], 7F8h
0x180006ac3  mov     r8d, eax
0x180006ac6  lea     rdx, EFS_API_ERROR
0x180006acd  mov     r9d, 6
0x180006ad3  call    fnEfsLogTrace1
0x180006ad8  jmp     loc_180006B9F
0x180006add  call    EfspCheckForNetSession
0x180006ae2  test    eax, eax
0x180006ae4  jz      short loc_180006B45
0x180006ae6  mov     edx, 1
0x180006aeb  cmp     [rsp+68h+var_38], dx
0x180006af0  jnz     short loc_180006AFA
0x180006af2  lea     ebx, [rdx+4]
0x180006af5  jmp     loc_180006B9F
0x180006afa  mov     r8d, 80h
0x180006b00  mov     rcx, rdi
0x180006b03  call    cs:__imp_EfsDllShareDecline
0x180006b0a  nop     dword ptr [rax+rax+00h]
0x180006b0f  test    eax, eax
0x180006b11  jz      short loc_180006B37
0x180006b13  call    cs:__imp_GetLastError
0x180006b1a  nop     dword ptr [rax+rax+00h]
0x180006b1f  mov     ebx, eax
0x180006b21  call    cs:__imp_GetLastError
0x180006b28  nop     dword ptr [rax+rax+00h]
0x180006b2d  mov     [rsp+68h+var_48], 809h
0x180006b35  jmp     short loc_180006AC3
0x180006b37  mov     rcx, rbp
0x180006b3a  call    EfspIsValidNetworkProtSeq
0x180006b3f  mov     ebx, eax
0x180006b41  test    eax, eax
0x180006b43  jnz     short loc_180006B9F
0x180006b45  mov     ecx, 10h; size
0x180006b4a  call    MIDL_user_allocate
0x180006b4f  mov     rdi, rax
0x180006b52  test    rax, rax
0x180006b55  jnz     short loc_180006B5C
0x180006b57  lea     ebx, [rax+8]
0x180006b5a  jmp     short loc_180006B9F
0x180006b5c  mov     rcx, [rsp+68h+var_30]
0x180006b61  lea     r9, [rax+8]
0x180006b65  mov     r8, rdi
0x180006b68  mov     edx, r14d
0x180006b6b  call    cs:__imp_EfsDllFileKeyInfoSrv
0x180006b72  nop     dword ptr [rax+rax+00h]
0x180006b77  mov     ebx, eax
0x180006b79  test    eax, eax
0x180006b7b  jnz     short loc_180006B89
0x180006b7d  cmp     qword ptr [rdi+8], 0
0x180006b82  jz      short loc_180006B97
0x180006b84  mov     [rsi], rdi
0x180006b87  jmp     short loc_180006B9F
0x180006b89  mov     rcx, [rdi+8]; void *
0x180006b8d  test    rcx, rcx
0x180006b90  jz      short loc_180006B97
0x180006b92  call    MIDL_user_free
0x180006b97  mov     rcx, rdi; void *
0x180006b9a  call    MIDL_user_free
0x180006b9f  call    cs:__imp_RpcRevertToSelf
0x180006ba6  nop     dword ptr [rax+rax+00h]
0x180006bab  mov     rcx, [rsp+68h+var_30]
0x180006bb0  test    rcx, rcx
0x180006bb3  jz      short loc_180006BC1
0x180006bb5  call    cs:__imp_EfsDllFreeHeap
0x180006bbc  nop     dword ptr [rax+rax+00h]
0x180006bc1  mov     eax, ebx
0x180006bc3  add     rsp, 40h
0x180006bc7  pop     r14
0x180006bc9  pop     rdi
0x180006bca  pop     rsi
0x180006bcb  pop     rbp
0x180006bcc  pop     rbx
0x180006bcd  retn
```

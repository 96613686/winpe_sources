# EfsRpcQueryUsersOnFile

- ea: `0x180006bb0`
- end: `0x180006d64`
- name: `EfsRpcQueryUsersOnFile`
- size: `436`
- prototype: `__int64 __fastcall(void *, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003510`
- `0x180003540`
- `0x180003604`
- `0x180006bb0`
- `0x1800076b4`
- `0x180007ae8`
- `0x18000b308`
- `0x18000b480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cd6`
- `RPCRT4!RpcRevertToSelf` at `0x180006d43`
- `RPCRT4!RpcRevertToSelf` at `0x180006d43`
- `RPCRT4!RpcImpersonateClient` at `0x180006c5b`
- `RPCRT4!RpcImpersonateClient` at `0x180006c5b`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006c43`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006c43`
- `EFSCORE!EfsDllDisabled` at `0x180006be3`
- `EFSCORE!EfsDllDisabled` at `0x180006be3`
- `EFSCORE!EfsDllShareDecline` at `0x180006ccc`
- `EFSCORE!EfsDllShareDecline` at `0x180006ccc`
- `EFSCORE!EfsDllFreeHeap` at `0x180006d53`
- `EFSCORE!EfsDllFreeHeap` at `0x180006d53`
- `EFSCORE!EfsDllQueryUsersOnFileSrv` at `0x180006d23`
- `EFSCORE!EfsDllQueryUsersOnFileSrv` at `0x180006d23`

## pseudocode

```c
__int64 __fastcall EfsRpcQueryUsersOnFile(void *a1, __int64 a2, _QWORD *a3)
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
  int v15; // ecx
  DWORD IsValidNetworkProtSeq; // eax
  int v17; // ecx
  char *v18; // rax
  void *v19; // rdi
  const WCHAR *v21; // [rsp+30h] [rbp-38h] BYREF
  __int16 v22; // [rsp+88h] [rbp+20h] BYREF

  v21 = 0;
  v22 = 0;
  if ( !EfsServerInitialized )
    return 50;
  if ( (unsigned __int8)EfsDllDisabled(a1) )
  {
    LastError = 6015;
    goto LABEL_30;
  }
  if ( !a3 )
  {
    LastError = 87;
    goto LABEL_30;
  }
  v7 = EfsEnforceClientAuthentication();
  LastError = v7;
  if ( !v7 )
  {
    LocalFileName = EfsDllGetLocalFileName(a2, 0, &v21, &v22);
    LastError = LocalFileName;
    if ( LocalFileName )
    {
      fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 136);
      goto LABEL_30;
    }
    v11 = RpcImpersonateClient(0);
    LastError = v11;
    if ( v11 )
    {
      fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v11, 6, 141);
      goto LABEL_30;
    }
    v13 = EfsEnsureLocalPath(v21);
    LastError = v13;
    if ( v13 )
    {
      fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 6, 147);
      goto LABEL_29;
    }
    if ( (unsigned int)EfspCheckForNetSession() )
    {
      if ( v22 == 1 )
      {
        LastError = 5;
LABEL_29:
        RpcRevertToSelf();
        goto LABEL_30;
      }
      if ( (unsigned int)EfsDllShareDecline(a2, 1, 128) )
      {
        LastError = GetLastError();
        fnEfsLogTrace1(v15, (unsigned int)EFS_API_ERROR, LastError, 6, 164);
        goto LABEL_29;
      }
      IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
      LastError = IsValidNetworkProtSeq;
      if ( IsValidNetworkProtSeq )
      {
        fnEfsLogTrace1(v17, (unsigned int)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 173);
        goto LABEL_29;
      }
    }
    v18 = (char *)MIDL_user_allocate(0x10u);
    v19 = v18;
    if ( v18 )
    {
      LastError = EfsDllQueryUsersOnFileSrv(v21, v18, v18 + 8);
      if ( LastError )
      {
        MIDL_user_free(v19);
        *a3 = 0;
      }
      else
      {
        *a3 = v19;
      }
    }
    else
    {
      LastError = 8;
    }
    goto LABEL_29;
  }
  fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v7, 6, 131);
LABEL_30:
  if ( v21 )
    EfsDllFreeHeap(v21);
  return LastError;
}

```

## disassembly

```asm
0x180006bb0  mov     r11, rsp
0x180006bb3  push    rbx
0x180006bb4  push    rbp
0x180006bb5  push    rsi
0x180006bb6  push    rdi
0x180006bb7  sub     rsp, 48h
0x180006bbb  xor     eax, eax
0x180006bbd  mov     qword ptr [r11-38h], 0
0x180006bc5  cmp     cs:EfsServerInitialized, al
0x180006bcb  mov     rsi, r8
0x180006bce  mov     rdi, rdx
0x180006bd1  mov     [r11+20h], ax
0x180006bd6  mov     rbp, rcx
0x180006bd9  jnz     short loc_180006BE3
0x180006bdb  lea     ebx, [rax+32h]
0x180006bde  jmp     loc_180006D59
0x180006be3  call    cs:__imp_EfsDllDisabled
0x180006be9  test    al, al
0x180006beb  jz      short loc_180006BF7
0x180006bed  mov     ebx, 177Fh
0x180006bf2  jmp     loc_180006D49
0x180006bf7  test    rsi, rsi
0x180006bfa  jnz     short loc_180006C04
0x180006bfc  lea     ebx, [rsi+57h]
0x180006bff  jmp     loc_180006D49
0x180006c04  call    EfsEnforceClientAuthentication
0x180006c09  mov     ebx, eax
0x180006c0b  test    eax, eax
0x180006c0d  jz      short loc_180006C31
0x180006c0f  mov     [rsp+68h+var_48], 483h
0x180006c17  mov     r9d, 6
0x180006c1d  lea     rdx, EFS_API_ERROR
0x180006c24  mov     r8d, eax
0x180006c27  call    fnEfsLogTrace1
0x180006c2c  jmp     loc_180006D49
0x180006c31  lea     r9, [rsp+68h+arg_18]
0x180006c39  xor     edx, edx
0x180006c3b  lea     r8, [rsp+68h+var_38]
0x180006c40  mov     rcx, rdi
0x180006c43  call    cs:__imp_EfsDllGetLocalFileName
0x180006c49  mov     ebx, eax
0x180006c4b  test    eax, eax
0x180006c4d  jz      short loc_180006C59
0x180006c4f  mov     [rsp+68h+var_48], 488h
0x180006c57  jmp     short loc_180006C17
0x180006c59  xor     ecx, ecx; BindingHandle
0x180006c5b  call    cs:__imp_RpcImpersonateClient
0x180006c61  mov     ebx, eax
0x180006c63  test    eax, eax
0x180006c65  jz      short loc_180006C71
0x180006c67  mov     [rsp+68h+var_48], 48Dh
0x180006c6f  jmp     short loc_180006C17
0x180006c71  mov     rcx, [rsp+68h+var_38]
0x180006c76  call    EfsEnsureLocalPath
0x180006c7b  mov     ebx, eax
0x180006c7d  test    eax, eax
0x180006c7f  jz      short loc_180006CA3
0x180006c81  mov     [rsp+68h+var_48], 493h
0x180006c89  mov     r9d, 6
0x180006c8f  lea     rdx, EFS_API_ERROR
0x180006c96  mov     r8d, eax
0x180006c99  call    fnEfsLogTrace1
0x180006c9e  jmp     loc_180006D43
0x180006ca3  call    EfspCheckForNetSession
0x180006ca8  test    eax, eax
0x180006caa  jz      short loc_180006D00
0x180006cac  mov     edx, 1
0x180006cb1  cmp     [rsp+68h+arg_18], dx
0x180006cb9  jnz     short loc_180006CC3
0x180006cbb  lea     ebx, [rdx+4]
0x180006cbe  jmp     loc_180006D43
0x180006cc3  mov     r8d, 80h
0x180006cc9  mov     rcx, rdi
0x180006ccc  call    cs:__imp_EfsDllShareDecline
0x180006cd2  test    eax, eax
0x180006cd4  jz      short loc_180006CE8
0x180006cd6  call    cs:__imp_GetLastError
0x180006cdc  mov     ebx, eax
0x180006cde  mov     [rsp+68h+var_48], 4A4h
0x180006ce6  jmp     short loc_180006C89
0x180006ce8  mov     rcx, rbp
0x180006ceb  call    EfspIsValidNetworkProtSeq
0x180006cf0  mov     ebx, eax
0x180006cf2  test    eax, eax
0x180006cf4  jz      short loc_180006D00
0x180006cf6  mov     [rsp+68h+var_48], 4ADh
0x180006cfe  jmp     short loc_180006C89
0x180006d00  mov     ecx, 10h; size
0x180006d05  call    MIDL_user_allocate
0x180006d0a  mov     rdi, rax
0x180006d0d  test    rax, rax
0x180006d10  jnz     short loc_180006D17
0x180006d12  lea     ebx, [rax+8]
0x180006d15  jmp     short loc_180006D43
0x180006d17  mov     rcx, [rsp+68h+var_38]
0x180006d1c  lea     r8, [rax+8]
0x180006d20  mov     rdx, rdi
0x180006d23  call    cs:__imp_EfsDllQueryUsersOnFileSrv
0x180006d29  mov     ebx, eax
0x180006d2b  test    eax, eax
0x180006d2d  jnz     short loc_180006D34
0x180006d2f  mov     [rsi], rdi
0x180006d32  jmp     short loc_180006D43
0x180006d34  mov     rcx, rdi; void *
0x180006d37  call    MIDL_user_free
0x180006d3c  mov     qword ptr [rsi], 0
0x180006d43  call    cs:__imp_RpcRevertToSelf
0x180006d49  mov     rcx, [rsp+68h+var_38]
0x180006d4e  test    rcx, rcx
0x180006d51  jz      short loc_180006D59
0x180006d53  call    cs:__imp_EfsDllFreeHeap
0x180006d59  mov     eax, ebx
0x180006d5b  add     rsp, 48h
0x180006d5f  pop     rdi
0x180006d60  pop     rsi
0x180006d61  pop     rbp
0x180006d62  pop     rbx
0x180006d63  retn
```

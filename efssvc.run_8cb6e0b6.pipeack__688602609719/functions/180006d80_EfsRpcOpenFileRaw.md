# EfsRpcOpenFileRaw

- ea: `0x180006d80`
- end: `0x180006f2c`
- name: `EfsRpcOpenFileRaw`
- size: `428`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800037b8`
- `0x180006d80`
- `0x180007f38`
- `0x180008404`
- `0x18000bf0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e94`
- `RPCRT4!RpcRevertToSelf` at `0x180006efa`
- `RPCRT4!RpcRevertToSelf` at `0x180006efa`
- `RPCRT4!RpcImpersonateClient` at `0x180006e46`
- `RPCRT4!RpcImpersonateClient` at `0x180006e46`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006e28`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006e28`
- `EFSCORE!EfsDllDisabled` at `0x180006db9`
- `EFSCORE!EfsDllDisabled` at `0x180006db9`
- `EFSCORE!EfsDllOpenFileRaw` at `0x180006eec`
- `EFSCORE!EfsDllOpenFileRaw` at `0x180006eec`
- `EFSCORE!EfsDllShareDecline` at `0x180006e84`
- `EFSCORE!EfsDllShareDecline` at `0x180006e84`
- `EFSCORE!EfsDllFreeHeap` at `0x180006f10`
- `EFSCORE!EfsDllFreeHeap` at `0x180006f10`

## pseudocode

```c
__int64 __fastcall EfsRpcOpenFileRaw(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v9; // eax
  int v10; // ecx
  DWORD LocalFileName; // eax
  int v12; // ecx
  RPC_STATUS v13; // eax
  int v14; // ecx
  unsigned int v15; // esi
  int v16; // ecx
  DWORD IsValidNetworkProtSeq; // eax
  int v18; // ecx
  __int16 v20; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v21[8]; // [rsp+38h] [rbp-40h] BYREF

  v21[0] = 0;
  v20 = 0;
  if ( !EfsServerInitialized )
    return 50;
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    LastError = 6015;
    goto LABEL_25;
  }
  if ( !a2 && !a3 )
  {
    LastError = 5;
    goto LABEL_25;
  }
  v9 = EfsEnforceClientAuthentication();
  LastError = v9;
  if ( !v9 )
  {
    *a2 = 0;
    LocalFileName = EfsDllGetLocalFileName(a3, 0, v21, &v20);
    LastError = LocalFileName;
    if ( LocalFileName )
    {
      fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 147);
      goto LABEL_25;
    }
    v13 = RpcImpersonateClient(0);
    LastError = v13;
    if ( v13 )
    {
      fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 6, 152);
      goto LABEL_25;
    }
    v15 = EfspCheckForNetSession();
    if ( v15 )
    {
      if ( v20 == 1 )
      {
        LastError = 5;
LABEL_24:
        RpcRevertToSelf();
        goto LABEL_25;
      }
      if ( (unsigned int)EfsDllShareDecline(a3, 0, 0) )
      {
        LastError = GetLastError();
        fnEfsLogTrace1(v16, (unsigned int)EFS_API_ERROR, LastError, 6, 171);
        goto LABEL_24;
      }
      IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
      LastError = IsValidNetworkProtSeq;
      if ( IsValidNetworkProtSeq )
      {
        fnEfsLogTrace1(v18, (unsigned int)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 180);
        goto LABEL_24;
      }
    }
    LastError = EfsDllOpenFileRaw(a3, v21[0], v15, a4, a2);
    goto LABEL_24;
  }
  fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 141);
LABEL_25:
  if ( v21[0] )
    EfsDllFreeHeap();
  return LastError;
}

```

## disassembly

```asm
0x180006d80  push    rbx
0x180006d82  push    rbp
0x180006d83  push    rsi
0x180006d84  push    rdi
0x180006d85  push    r14
0x180006d87  push    r15
0x180006d89  sub     rsp, 48h
0x180006d8d  xor     eax, eax
0x180006d8f  mov     [rsp+78h+var_40], 0
0x180006d98  cmp     cs:EfsServerInitialized, al
0x180006d9e  mov     r15d, r9d
0x180006da1  mov     rdi, r8
0x180006da4  mov     [rsp+78h+var_48], ax
0x180006da9  mov     r14, rdx
0x180006dac  mov     rbp, rcx
0x180006daf  jnz     short loc_180006DB9
0x180006db1  lea     ebx, [rax+32h]
0x180006db4  jmp     loc_180006F1C
0x180006db9  call    cs:__imp_EfsDllDisabled
0x180006dc0  nop     dword ptr [rax+rax+00h]
0x180006dc5  test    al, al
0x180006dc7  jz      short loc_180006DD3
0x180006dc9  mov     ebx, 177Fh
0x180006dce  jmp     loc_180006F06
0x180006dd3  test    r14, r14
0x180006dd6  jnz     short loc_180006DE5
0x180006dd8  test    rdi, rdi
0x180006ddb  jnz     short loc_180006DE5
0x180006ddd  lea     ebx, [rdi+5]
0x180006de0  jmp     loc_180006F06
0x180006de5  call    EfsEnforceClientAuthentication
0x180006dea  mov     ebx, eax
0x180006dec  test    eax, eax
0x180006dee  jz      short loc_180006E12
0x180006df0  mov     dword ptr [rsp+78h+var_58], 8Dh
0x180006df8  mov     r9d, 6
0x180006dfe  lea     rdx, EFS_API_ERROR
0x180006e05  mov     r8d, eax
0x180006e08  call    fnEfsLogTrace1
0x180006e0d  jmp     loc_180006F06
0x180006e12  lea     r9, [rsp+78h+var_48]
0x180006e17  mov     qword ptr [r14], 0
0x180006e1e  lea     r8, [rsp+78h+var_40]
0x180006e23  xor     edx, edx
0x180006e25  mov     rcx, rdi
0x180006e28  call    cs:__imp_EfsDllGetLocalFileName
0x180006e2f  nop     dword ptr [rax+rax+00h]
0x180006e34  mov     ebx, eax
0x180006e36  test    eax, eax
0x180006e38  jz      short loc_180006E44
0x180006e3a  mov     dword ptr [rsp+78h+var_58], 93h
0x180006e42  jmp     short loc_180006DF8
0x180006e44  xor     ecx, ecx; BindingHandle
0x180006e46  call    cs:__imp_RpcImpersonateClient
0x180006e4d  nop     dword ptr [rax+rax+00h]
0x180006e52  mov     ebx, eax
0x180006e54  test    eax, eax
0x180006e56  jz      short loc_180006E62
0x180006e58  mov     dword ptr [rsp+78h+var_58], 98h
0x180006e60  jmp     short loc_180006DF8
0x180006e62  call    EfspCheckForNetSession
0x180006e67  mov     esi, eax
0x180006e69  test    eax, eax
0x180006e6b  jz      short loc_180006ED9
0x180006e6d  cmp     [rsp+78h+var_48], 1
0x180006e73  jnz     short loc_180006E7C
0x180006e75  mov     ebx, 5
0x180006e7a  jmp     short loc_180006EFA
0x180006e7c  xor     r8d, r8d
0x180006e7f  xor     edx, edx
0x180006e81  mov     rcx, rdi
0x180006e84  call    cs:__imp_EfsDllShareDecline
0x180006e8b  nop     dword ptr [rax+rax+00h]
0x180006e90  test    eax, eax
0x180006e92  jz      short loc_180006EC1
0x180006e94  call    cs:__imp_GetLastError
0x180006e9b  nop     dword ptr [rax+rax+00h]
0x180006ea0  mov     ebx, eax
0x180006ea2  mov     dword ptr [rsp+78h+var_58], 0ABh
0x180006eaa  mov     r9d, 6
0x180006eb0  lea     rdx, EFS_API_ERROR
0x180006eb7  mov     r8d, eax
0x180006eba  call    fnEfsLogTrace1
0x180006ebf  jmp     short loc_180006EFA
0x180006ec1  mov     rcx, rbp
0x180006ec4  call    EfspIsValidNetworkProtSeq
0x180006ec9  mov     ebx, eax
0x180006ecb  test    eax, eax
0x180006ecd  jz      short loc_180006ED9
0x180006ecf  mov     dword ptr [rsp+78h+var_58], 0B4h
0x180006ed7  jmp     short loc_180006EAA
0x180006ed9  mov     rdx, [rsp+78h+var_40]
0x180006ede  mov     r9d, r15d
0x180006ee1  mov     r8d, esi
0x180006ee4  mov     [rsp+78h+var_58], r14
0x180006ee9  mov     rcx, rdi
0x180006eec  call    cs:__imp_EfsDllOpenFileRaw
0x180006ef3  nop     dword ptr [rax+rax+00h]
0x180006ef8  mov     ebx, eax
0x180006efa  call    cs:__imp_RpcRevertToSelf
0x180006f01  nop     dword ptr [rax+rax+00h]
0x180006f06  mov     rcx, [rsp+78h+var_40]
0x180006f0b  test    rcx, rcx
0x180006f0e  jz      short loc_180006F1C
0x180006f10  call    cs:__imp_EfsDllFreeHeap
0x180006f17  nop     dword ptr [rax+rax+00h]
0x180006f1c  mov     eax, ebx
0x180006f1e  add     rsp, 48h
0x180006f22  pop     r15
0x180006f24  pop     r14
0x180006f26  pop     rdi
0x180006f27  pop     rsi
0x180006f28  pop     rbp
0x180006f29  pop     rbx
0x180006f2a  retn
```

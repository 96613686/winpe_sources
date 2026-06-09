# EfsRpcWriteFileRaw

- ea: `0x180007a70`
- end: `0x180007b26`
- name: `EfsRpcWriteFileRaw`
- size: `182`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x1800037b8`
- `0x180007a70`
- `0x18000bf0c`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180007aef`
- `RPCRT4!RpcRevertToSelf` at `0x180007aef`
- `RPCRT4!RpcImpersonateClient` at `0x180007abf`
- `RPCRT4!RpcImpersonateClient` at `0x180007abf`
- `RPCRT4!RpcRaiseException` at `0x180007b19`
- `RPCRT4!RpcRaiseException` at `0x180007b19`
- `EFSCORE!EfsDllWriteFileRaw` at `0x180007ae1`
- `EFSCORE!EfsDllWriteFileRaw` at `0x180007ae1`

## pseudocode

```c
__int64 __fastcall EfsRpcWriteFileRaw(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  RPC_STATUS v6; // ebx
  RPC_STATUS v7; // eax
  __int64 v8; // rcx

  if ( !a2 || !a1 )
  {
    v6 = 5;
    goto LABEL_11;
  }
  v4 = EfsEnforceClientAuthentication();
  v6 = v4;
  if ( v4 )
  {
    fnEfsLogTrace1(v5, (__int64)EFS_API_ERROR, v4, 6, 106);
    goto LABEL_11;
  }
  v7 = RpcImpersonateClient(0);
  v6 = v7;
  if ( v7 )
  {
    fnEfsLogTrace1(v8, (__int64)EFS_API_ERROR, v7, 6, 111);
    goto LABEL_11;
  }
  v6 = EfsDllWriteFileRaw(a1, a2);
  RpcRevertToSelf();
  if ( v6 )
LABEL_11:
    RpcRaiseException(v6);
  return 0;
}

```

## disassembly

```asm
0x180007a70  mov     [rsp+arg_0], rbx
0x180007a75  mov     [rsp+arg_8], rsi
0x180007a7a  push    rdi
0x180007a7b  sub     rsp, 30h
0x180007a7f  mov     rsi, rdx
0x180007a82  mov     rdi, rcx
0x180007a85  test    rdx, rdx
0x180007a88  jz      loc_180007B12
0x180007a8e  test    rcx, rcx
0x180007a91  jz      short loc_180007B12
0x180007a93  call    EfsEnforceClientAuthentication
0x180007a98  mov     ebx, eax
0x180007a9a  test    eax, eax
0x180007a9c  jz      short loc_180007ABD
0x180007a9e  mov     [rsp+38h+var_18], 16Ah
0x180007aa6  mov     r9d, 6
0x180007aac  lea     rdx, EFS_API_ERROR
0x180007ab3  mov     r8d, eax
0x180007ab6  call    fnEfsLogTrace1
0x180007abb  jmp     short loc_180007B17
0x180007abd  xor     ecx, ecx; BindingHandle
0x180007abf  call    cs:__imp_RpcImpersonateClient
0x180007ac6  nop     dword ptr [rax+rax+00h]
0x180007acb  mov     ebx, eax
0x180007acd  test    eax, eax
0x180007acf  jz      short loc_180007ADB
0x180007ad1  mov     [rsp+38h+var_18], 16Fh
0x180007ad9  jmp     short loc_180007AA6
0x180007adb  mov     rdx, rsi
0x180007ade  mov     rcx, rdi
0x180007ae1  call    cs:__imp_EfsDllWriteFileRaw
0x180007ae8  nop     dword ptr [rax+rax+00h]
0x180007aed  mov     ebx, eax
0x180007aef  call    cs:__imp_RpcRevertToSelf
0x180007af6  nop     dword ptr [rax+rax+00h]
0x180007afb  test    ebx, ebx
0x180007afd  jnz     short loc_180007B17
0x180007aff  mov     rbx, [rsp+38h+arg_0]
0x180007b04  xor     eax, eax
0x180007b06  mov     rsi, [rsp+38h+arg_8]
0x180007b0b  add     rsp, 30h
0x180007b0f  pop     rdi
0x180007b10  retn
0x180007b12  mov     ebx, 5
0x180007b17  mov     ecx, ebx; exception
0x180007b19  call    cs:__imp_RpcRaiseException
0x180007b20  nop     dword ptr [rax+rax+00h]
0x180007b25  int     3; Trap to Debugger
```

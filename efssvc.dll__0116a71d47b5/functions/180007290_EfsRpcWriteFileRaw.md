# EfsRpcWriteFileRaw

- ea: `0x180007290`
- end: `0x180007329`
- name: `EfsRpcWriteFileRaw`
- size: `153`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x180003604`
- `0x180007290`
- `0x18000b308`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800072ff`
- `RPCRT4!RpcRevertToSelf` at `0x1800072ff`
- `RPCRT4!RpcImpersonateClient` at `0x1800072db`
- `RPCRT4!RpcImpersonateClient` at `0x1800072db`
- `RPCRT4!RpcRaiseException` at `0x180007322`
- `RPCRT4!RpcRaiseException` at `0x180007322`
- `EFSCORE!EfsDllWriteFileRaw` at `0x1800072f7`
- `EFSCORE!EfsDllWriteFileRaw` at `0x1800072f7`

## pseudocode

```c
__int64 __fastcall EfsRpcWriteFileRaw(__int64 a1, __int64 a2)
{
  RPC_STATUS v4; // eax
  int v5; // ecx
  RPC_STATUS v6; // ebx
  RPC_STATUS v7; // eax
  int v8; // ecx

  if ( !a2 || !a1 )
  {
    v6 = 5;
    goto LABEL_11;
  }
  v4 = EfsEnforceClientAuthentication();
  v6 = v4;
  if ( v4 )
  {
    fnEfsLogTrace1(v5, (unsigned int)EFS_API_ERROR, v4, 6, 106);
    goto LABEL_11;
  }
  v7 = RpcImpersonateClient(0);
  v6 = v7;
  if ( v7 )
  {
    fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v7, 6, 111);
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
0x180007290  mov     [rsp+arg_0], rbx
0x180007295  mov     [rsp+arg_8], rsi
0x18000729a  push    rdi
0x18000729b  sub     rsp, 30h
0x18000729f  mov     rsi, rdx
0x1800072a2  mov     rdi, rcx
0x1800072a5  test    rdx, rdx
0x1800072a8  jz      short loc_18000731B
0x1800072aa  test    rcx, rcx
0x1800072ad  jz      short loc_18000731B
0x1800072af  call    EfsEnforceClientAuthentication
0x1800072b4  mov     ebx, eax
0x1800072b6  test    eax, eax
0x1800072b8  jz      short loc_1800072D9
0x1800072ba  mov     [rsp+38h+var_18], 16Ah
0x1800072c2  mov     r9d, 6
0x1800072c8  lea     rdx, EFS_API_ERROR
0x1800072cf  mov     r8d, eax
0x1800072d2  call    fnEfsLogTrace1
0x1800072d7  jmp     short loc_180007320
0x1800072d9  xor     ecx, ecx; BindingHandle
0x1800072db  call    cs:__imp_RpcImpersonateClient
0x1800072e1  mov     ebx, eax
0x1800072e3  test    eax, eax
0x1800072e5  jz      short loc_1800072F1
0x1800072e7  mov     [rsp+38h+var_18], 16Fh
0x1800072ef  jmp     short loc_1800072C2
0x1800072f1  mov     rdx, rsi
0x1800072f4  mov     rcx, rdi
0x1800072f7  call    cs:__imp_EfsDllWriteFileRaw
0x1800072fd  mov     ebx, eax
0x1800072ff  call    cs:__imp_RpcRevertToSelf
0x180007305  test    ebx, ebx
0x180007307  jnz     short loc_180007320
0x180007309  mov     rbx, [rsp+38h+arg_0]
0x18000730e  xor     eax, eax
0x180007310  mov     rsi, [rsp+38h+arg_8]
0x180007315  add     rsp, 30h
0x180007319  pop     rdi
0x18000731a  retn
0x18000731b  mov     ebx, 5
0x180007320  mov     ecx, ebx; exception
0x180007322  call    cs:__imp_RpcRaiseException
```

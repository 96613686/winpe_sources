# EfsRpcReadFileRaw

- ea: `0x180006d70`
- end: `0x180006de9`
- name: `EfsRpcReadFileRaw`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180003604`
- `0x180006d70`
- `0x18000b308`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180006de2`
- `RPCRT4!RpcRaiseException` at `0x180006de2`
- `EFSCORE!EfsDllReadFileRaw` at `0x180006dbf`
- `EFSCORE!EfsDllReadFileRaw` at `0x180006dbf`

## pseudocode

```c
__int64 __fastcall EfsRpcReadFileRaw(__int64 a1, __int64 a2)
{
  RPC_STATUS v4; // eax
  int v5; // ecx
  RPC_STATUS v6; // ebx
  __int64 result; // rax

  if ( !a2 || !a1 )
  {
    v6 = 5;
    goto LABEL_8;
  }
  v4 = EfsEnforceClientAuthentication();
  v6 = v4;
  if ( v4 )
  {
    fnEfsLogTrace1(v5, (unsigned int)EFS_API_ERROR, v4, 6, 45);
    goto LABEL_8;
  }
  result = EfsDllReadFileRaw(a1, a2);
  v6 = result;
  if ( (_DWORD)result )
LABEL_8:
    RpcRaiseException(v6);
  return result;
}

```

## disassembly

```asm
0x180006d70  mov     [rsp+arg_0], rbx
0x180006d75  mov     [rsp+arg_8], rsi
0x180006d7a  push    rdi
0x180006d7b  sub     rsp, 30h
0x180006d7f  mov     rsi, rdx
0x180006d82  mov     rdi, rcx
0x180006d85  test    rdx, rdx
0x180006d88  jz      short loc_180006DDB
0x180006d8a  test    rcx, rcx
0x180006d8d  jz      short loc_180006DDB
0x180006d8f  call    EfsEnforceClientAuthentication
0x180006d94  mov     ebx, eax
0x180006d96  test    eax, eax
0x180006d98  jz      short loc_180006DB9
0x180006d9a  mov     r9d, 6
0x180006da0  mov     [rsp+38h+var_18], 12Dh
0x180006da8  mov     r8d, eax
0x180006dab  lea     rdx, EFS_API_ERROR
0x180006db2  call    fnEfsLogTrace1
0x180006db7  jmp     short loc_180006DE0
0x180006db9  mov     rdx, rsi
0x180006dbc  mov     rcx, rdi
0x180006dbf  call    cs:__imp_EfsDllReadFileRaw
0x180006dc5  mov     ebx, eax
0x180006dc7  test    eax, eax
0x180006dc9  jnz     short loc_180006DE0
0x180006dcb  mov     rbx, [rsp+38h+arg_0]
0x180006dd0  mov     rsi, [rsp+38h+arg_8]
0x180006dd5  add     rsp, 30h
0x180006dd9  pop     rdi
0x180006dda  retn
0x180006ddb  mov     ebx, 5
0x180006de0  mov     ecx, ebx; exception
0x180006de2  call    cs:__imp_RpcRaiseException
```

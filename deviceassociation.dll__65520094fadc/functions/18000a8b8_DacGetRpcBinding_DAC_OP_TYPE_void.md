# DacGetRpcBinding(DAC_OP_TYPE,void * *)

- ea: `0x18000a8b8`
- end: `0x18000a9a4`
- name: `?DacGetRpcBinding@@YAJW4DAC_OP_TYPE@@PEAPEAX@Z`
- size: `236`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002284`
- `0x18000ae80`
- `0x18000afc0`

## callees

- `0x18000a8b8`

## import_xrefs

- `RPCRT4!RpcSsDestroyClientContext` at `0x18000a98c`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18000a98c`
- `RPCRT4!RpcBindingFree` at `0x18000a97f`
- `RPCRT4!RpcBindingFree` at `0x18000a97f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000a935`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000a935`
- `RPCRT4!RpcStringFreeW` at `0x18000a95d`
- `RPCRT4!RpcStringFreeW` at `0x18000a95d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000a949`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000a949`

## pseudocode

```c
__int64 __fastcall DacGetRpcBinding(int a1, RPC_BINDING_HANDLE *a2)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rcx
  RPC_STATUS v10; // edi
  RPC_WSTR String; // [rsp+50h] [rbp+18h] BYREF

  String = 0;
  v3 = a1 - 1;
  if ( !v3 )
    goto LABEL_10;
  v4 = v3 - 1;
  if ( !v4 )
    goto LABEL_10;
  v5 = v4 - 1;
  if ( !v5 )
    goto LABEL_10;
  v6 = v5 - 1;
  if ( !v6 )
  {
    v9 = L"145857ef-d848-4a7e-b544-c1984d26cf05";
    goto LABEL_11;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
LABEL_10:
    v9 = L"49541cea-a719-4e75-8d58-a3a7bfff960e";
    goto LABEL_11;
  }
  if ( v7 != 1 )
    return (unsigned int)-2147418113;
  v9 = L"80b4038a-1d09-4c05-b1b6-249a4c2e0736";
LABEL_11:
  v8 = 0;
  *a2 = 0;
  v10 = RpcStringBindingComposeW(v9, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  if ( !v10 )
    v10 = RpcBindingFromStringBindingW(String, a2);
  if ( String )
    RpcStringFreeW(&String);
  if ( v10 )
  {
    if ( v10 < 0 )
      v8 = v10;
    else
      v8 = (unsigned __int16)v10 | 0x80010000;
    if ( *a2 && RpcBindingFree(a2) )
      RpcSsDestroyClientContext(a2);
  }
  return v8;
}

```

## disassembly

```asm
0x18000a8b8  mov     [rsp+arg_0], rbx
0x18000a8bd  mov     [rsp+arg_8], rsi
0x18000a8c2  push    rdi
0x18000a8c3  sub     rsp, 30h
0x18000a8c7  mov     [rsp+38h+String], 0
0x18000a8d0  mov     rsi, rdx
0x18000a8d3  sub     ecx, 1
0x18000a8d6  jz      short loc_18000A90D
0x18000a8d8  sub     ecx, 1
0x18000a8db  jz      short loc_18000A90D
0x18000a8dd  sub     ecx, 1
0x18000a8e0  jz      short loc_18000A90D
0x18000a8e2  sub     ecx, 1
0x18000a8e5  jz      short loc_18000A904
0x18000a8e7  sub     ecx, 1
0x18000a8ea  jz      short loc_18000A90D
0x18000a8ec  cmp     ecx, 1
0x18000a8ef  jz      short loc_18000A8FB
0x18000a8f1  mov     ebx, 8000FFFFh
0x18000a8f6  jmp     loc_18000A992
0x18000a8fb  lea     rcx, a80b4038a1d094c; "80b4038a-1d09-4c05-b1b6-249a4c2e0736"
0x18000a902  jmp     short loc_18000A914
0x18000a904  lea     rcx, a145857efD8484a; "145857ef-d848-4a7e-b544-c1984d26cf05"
0x18000a90b  jmp     short loc_18000A914
0x18000a90d  lea     rcx, ObjUuid; "49541cea-a719-4e75-8d58-a3a7bfff960e"
0x18000a914  xor     ebx, ebx
0x18000a916  lea     rax, [rsp+38h+String]
0x18000a91b  mov     [rdx], rbx
0x18000a91e  xor     r9d, r9d; Endpoint
0x18000a921  mov     [rsp+38h+StringBinding], rax; StringBinding
0x18000a926  lea     rdx, ProtSeq; "ncalrpc"
0x18000a92d  xor     r8d, r8d; NetworkAddr
0x18000a930  mov     [rsp+38h+Options], rbx; Options
0x18000a935  call    cs:__imp_RpcStringBindingComposeW
0x18000a93b  mov     edi, eax
0x18000a93d  test    eax, eax
0x18000a93f  jnz     short loc_18000A951
0x18000a941  mov     rcx, [rsp+38h+String]; StringBinding
0x18000a946  mov     rdx, rsi; Binding
0x18000a949  call    cs:__imp_RpcBindingFromStringBindingW
0x18000a94f  mov     edi, eax
0x18000a951  cmp     [rsp+38h+String], rbx
0x18000a956  jz      short loc_18000A963
0x18000a958  lea     rcx, [rsp+38h+String]; String
0x18000a95d  call    cs:__imp_RpcStringFreeW
0x18000a963  test    edi, edi
0x18000a965  jz      short loc_18000A992
0x18000a967  js      short loc_18000A974
0x18000a969  movzx   ebx, di
0x18000a96c  or      ebx, 80010000h
0x18000a972  jmp     short loc_18000A976
0x18000a974  mov     ebx, edi
0x18000a976  cmp     qword ptr [rsi], 0
0x18000a97a  jz      short loc_18000A992
0x18000a97c  mov     rcx, rsi; Binding
0x18000a97f  call    cs:__imp_RpcBindingFree
0x18000a985  test    eax, eax
0x18000a987  jz      short loc_18000A992
0x18000a989  mov     rcx, rsi; ContextHandle
0x18000a98c  call    cs:__imp_RpcSsDestroyClientContext
0x18000a992  mov     rsi, [rsp+38h+arg_8]
0x18000a997  mov     eax, ebx
0x18000a999  mov     rbx, [rsp+38h+arg_0]
0x18000a99e  add     rsp, 30h
0x18000a9a2  pop     rdi
0x18000a9a3  retn
```

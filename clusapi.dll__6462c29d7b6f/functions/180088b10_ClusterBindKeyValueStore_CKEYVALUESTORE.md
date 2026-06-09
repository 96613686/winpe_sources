# ClusterBindKeyValueStore(_CKEYVALUESTORE *)

- ea: `0x180088b10`
- end: `0x180088b99`
- name: `?ClusterBindKeyValueStore@@YAKPEAU_CKEYVALUESTORE@@@Z`
- size: `137`
- prototype: `unsigned int __fastcall(struct _CKEYVALUESTORE *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180088dec`
- `0x18008930c`
- `0x1800897fc`
- `0x180089bd0`
- `0x18008a644`

## callees

- `0x180088ac8`
- `0x180088b10`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x180088b7c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180088b7c`
- `RPCRT4!RpcStringBindingComposeW` at `0x180088b68`
- `RPCRT4!RpcStringBindingComposeW` at `0x180088b68`
- `RPCRT4!RpcBindingFree` at `0x180088b2a`
- `RPCRT4!RpcBindingFree` at `0x180088b2a`

## pseudocode

```c
__int64 __fastcall ClusterBindKeyValueStore(RPC_BINDING_HANDLE *a1)
{
  RPC_BINDING_HANDLE *v1; // rbx
  unsigned __int16 *v3; // r9
  unsigned int v4; // edi
  RPC_WSTR StringBinding; // [rsp+40h] [rbp+8h] BYREF

  v1 = a1 + 4;
  if ( a1[4] )
  {
    RpcBindingFree(a1 + 4);
    *v1 = 0;
  }
  v3 = (unsigned __int16 *)a1[2];
  StringBinding = 0;
  v4 = RpcStringBindingComposeW(
         (RPC_WSTR)L"CBD0E917-B1B3-4465-98CF-56DE685DCD9C",
         (RPC_WSTR)L"ncalrpc",
         0,
         v3,
         0,
         &StringBinding);
  if ( !v4 )
    RpcBindingFromStringBindingW(StringBinding, v1);
  RpcString::~RpcString((RpcString *)&StringBinding);
  return v4;
}

```

## disassembly

```asm
0x180088b10  mov     [rsp+arg_8], rbx
0x180088b15  push    rdi
0x180088b16  sub     rsp, 30h
0x180088b1a  lea     rbx, [rcx+20h]
0x180088b1e  mov     rdi, rcx
0x180088b21  cmp     qword ptr [rbx], 0
0x180088b25  jz      short loc_180088B37
0x180088b27  mov     rcx, rbx; Binding
0x180088b2a  call    cs:__imp_RpcBindingFree
0x180088b30  mov     qword ptr [rbx], 0
0x180088b37  mov     r9, [rdi+10h]; Endpoint
0x180088b3b  lea     rax, [rsp+38h+arg_0]
0x180088b40  mov     [rsp+38h+StringBinding], rax; StringBinding
0x180088b45  lea     rdx, aNcalrpc; "ncalrpc"
0x180088b4c  xor     r8d, r8d; NetworkAddr
0x180088b4f  mov     [rsp+38h+Options], 0; Options
0x180088b58  lea     rcx, aCbd0e917B1b344; "CBD0E917-B1B3-4465-98CF-56DE685DCD9C"
0x180088b5f  mov     [rsp+38h+arg_0], 0
0x180088b68  call    cs:__imp_RpcStringBindingComposeW
0x180088b6e  mov     edi, eax
0x180088b70  test    eax, eax
0x180088b72  jnz     short loc_180088B82
0x180088b74  mov     rcx, [rsp+38h+arg_0]; StringBinding
0x180088b79  mov     rdx, rbx; Binding
0x180088b7c  call    cs:__imp_RpcBindingFromStringBindingW
0x180088b82  lea     rcx, [rsp+38h+arg_0]; this
0x180088b87  call    ??1RpcString@@QEAA@XZ; RpcString::~RpcString(void)
0x180088b8c  mov     rbx, [rsp+38h+arg_8]
0x180088b91  mov     eax, edi
0x180088b93  add     rsp, 30h
0x180088b97  pop     rdi
0x180088b98  retn
```

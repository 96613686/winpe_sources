# PubSebiGetRpcBindingHandle(void * *)

- ea: `0x1801729f0`
- end: `0x180172a7a`
- name: `?PubSebiGetRpcBindingHandle@@YAJPEAPEAX@Z`
- size: `138`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801725c4`
- `0x1801727a8`
- `0x1801728a4`

## callees

- `0x1801729f0`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180172a4d`
- `RPCRT4!RpcStringBindingComposeW` at `0x180172a4d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180172a65`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180172a65`
- `RPCRT4!RpcStringFreeW` at `0x180172a72`
- `RPCRT4!RpcStringFreeW` at `0x180172a72`

## string_xrefs

- `0x180172a38`: `Security=Impersonation Dynamic True`

## pseudocode

```c
__int64 __fastcall PubSebiGetRpcBindingHandle(void **a1)
{
  unsigned int v1; // ebx
  RPC_WSTR String; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  String = 0;
  if ( !PubSebiServiceHandle )
  {
    v1 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           0,
           (RPC_WSTR)L"csebpub",
           (RPC_WSTR)L"Security=Impersonation Dynamic True",
           &String);
    if ( !v1 )
    {
      v1 = RpcBindingFromStringBindingW(String, &PubSebiServiceHandle);
      RpcStringFreeW(&String);
    }
  }
  *a1 = PubSebiServiceHandle;
  return v1;
}

```

## disassembly

```asm
0x1801729f0  mov     [rsp+arg_8], rbx
0x1801729f5  push    rdi
0x1801729f6  sub     rsp, 30h
0x1801729fa  xor     ebx, ebx
0x1801729fc  mov     rdi, rcx
0x1801729ff  cmp     cs:?PubSebiServiceHandle@@3PEAXEA, rbx; void * PubSebiServiceHandle
0x180172a06  mov     [rsp+38h+String], rbx
0x180172a0b  jz      short loc_180172A24
0x180172a0d  mov     rax, cs:?PubSebiServiceHandle@@3PEAXEA; void * PubSebiServiceHandle
0x180172a14  mov     [rdi], rax
0x180172a17  mov     eax, ebx
0x180172a19  mov     rbx, [rsp+38h+arg_8]
0x180172a1e  add     rsp, 30h
0x180172a22  pop     rdi
0x180172a23  retn
0x180172a24  lea     rax, [rsp+38h+String]
0x180172a29  xor     r8d, r8d; NetworkAddr
0x180172a2c  mov     [rsp+38h+StringBinding], rax; StringBinding
0x180172a31  lea     r9, Endpoint; "csebpub"
0x180172a38  lea     rax, Options; "Security=Impersonation Dynamic True"
0x180172a3f  xor     ecx, ecx; ObjUuid
0x180172a41  lea     rdx, ProtSeq; "ncalrpc"
0x180172a48  mov     [rsp+38h+Options], rax; Options
0x180172a4d  call    cs:__imp_RpcStringBindingComposeW
0x180172a53  mov     ebx, eax
0x180172a55  test    eax, eax
0x180172a57  jnz     short loc_180172A0D
0x180172a59  mov     rcx, [rsp+38h+String]; StringBinding
0x180172a5e  lea     rdx, ?PubSebiServiceHandle@@3PEAXEA; Binding
0x180172a65  call    cs:__imp_RpcBindingFromStringBindingW
0x180172a6b  lea     rcx, [rsp+38h+String]; String
0x180172a70  mov     ebx, eax
0x180172a72  call    cs:__imp_RpcStringFreeW
0x180172a78  jmp     short loc_180172A0D
```

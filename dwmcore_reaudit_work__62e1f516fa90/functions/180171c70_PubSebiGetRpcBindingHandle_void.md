# PubSebiGetRpcBindingHandle(void * *)

- ea: `0x180171c70`
- end: `0x180171cfa`
- name: `?PubSebiGetRpcBindingHandle@@YAJPEAPEAX@Z`
- size: `138`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180171844`
- `0x180171a28`
- `0x180171b24`

## callees

- `0x180171c70`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180171ccd`
- `RPCRT4!RpcStringBindingComposeW` at `0x180171ccd`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180171ce5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180171ce5`
- `RPCRT4!RpcStringFreeW` at `0x180171cf2`
- `RPCRT4!RpcStringFreeW` at `0x180171cf2`

## string_xrefs

- `0x180171cb8`: `Security=Impersonation Dynamic True`

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
0x180171c70  mov     [rsp+arg_8], rbx
0x180171c75  push    rdi
0x180171c76  sub     rsp, 30h
0x180171c7a  xor     ebx, ebx
0x180171c7c  mov     rdi, rcx
0x180171c7f  cmp     cs:?PubSebiServiceHandle@@3PEAXEA, rbx; void * PubSebiServiceHandle
0x180171c86  mov     [rsp+38h+String], rbx
0x180171c8b  jz      short loc_180171CA4
0x180171c8d  mov     rax, cs:?PubSebiServiceHandle@@3PEAXEA; void * PubSebiServiceHandle
0x180171c94  mov     [rdi], rax
0x180171c97  mov     eax, ebx
0x180171c99  mov     rbx, [rsp+38h+arg_8]
0x180171c9e  add     rsp, 30h
0x180171ca2  pop     rdi
0x180171ca3  retn
0x180171ca4  lea     rax, [rsp+38h+String]
0x180171ca9  xor     r8d, r8d; NetworkAddr
0x180171cac  mov     [rsp+38h+StringBinding], rax; StringBinding
0x180171cb1  lea     r9, Endpoint; "csebpub"
0x180171cb8  lea     rax, Options; "Security=Impersonation Dynamic True"
0x180171cbf  xor     ecx, ecx; ObjUuid
0x180171cc1  lea     rdx, ProtSeq; "ncalrpc"
0x180171cc8  mov     [rsp+38h+Options], rax; Options
0x180171ccd  call    cs:__imp_RpcStringBindingComposeW
0x180171cd3  mov     ebx, eax
0x180171cd5  test    eax, eax
0x180171cd7  jnz     short loc_180171C8D
0x180171cd9  mov     rcx, [rsp+38h+String]; StringBinding
0x180171cde  lea     rdx, ?PubSebiServiceHandle@@3PEAXEA; Binding
0x180171ce5  call    cs:__imp_RpcBindingFromStringBindingW
0x180171ceb  lea     rcx, [rsp+38h+String]; String
0x180171cf0  mov     ebx, eax
0x180171cf2  call    cs:__imp_RpcStringFreeW
0x180171cf8  jmp     short loc_180171C8D
```

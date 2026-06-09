# EfspIsValidNetworkProtSeq

- ea: `0x180007ae8`
- end: `0x180007ba1`
- name: `EfspIsValidNetworkProtSeq`
- size: `185`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800055b0`
- `0x1800058a0`
- `0x180005bc0`
- `0x1800063c0`
- `0x1800065a0`
- `0x180006710`
- `0x180006a00`
- `0x180006bb0`
- `0x180007810`

## callees

- `0x180007ae8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007b4a`
- `msvcrt!_wcsicmp` at `0x180007b60`
- `msvcrt!_wcsicmp` at `0x180007b4a`
- `msvcrt!_wcsicmp` at `0x180007b60`
- `RPCRT4!RpcStringBindingParseW` at `0x180007b32`
- `RPCRT4!RpcStringBindingParseW` at `0x180007b32`
- `RPCRT4!RpcStringFreeW` at `0x180007b80`
- `RPCRT4!RpcStringFreeW` at `0x180007b93`
- `RPCRT4!RpcStringFreeW` at `0x180007b80`
- `RPCRT4!RpcStringFreeW` at `0x180007b93`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180007b05`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180007b05`

## pseudocode

```c
__int64 __fastcall EfspIsValidNetworkProtSeq(void *a1)
{
  unsigned int v1; // ebx
  RPC_WSTR Protseq; // [rsp+48h] [rbp+10h] BYREF
  RPC_WSTR StringBinding; // [rsp+50h] [rbp+18h] BYREF

  Protseq = 0;
  StringBinding = 0;
  v1 = RpcBindingToStringBindingW(a1, &StringBinding);
  if ( !v1 )
  {
    v1 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    if ( !v1 )
    {
      if ( _wcsicmp(Protseq, L"ncacn_np") && _wcsicmp(Protseq, L"ncalrpc") )
        v1 = 5;
      else
        v1 = 0;
    }
  }
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v1;
}

```

## disassembly

```asm
0x180007ae8  push    rbx
0x180007aea  sub     rsp, 30h
0x180007aee  lea     rdx, [rsp+38h+StringBinding]; StringBinding
0x180007af3  mov     [rsp+38h+Protseq], 0
0x180007afc  mov     [rsp+38h+StringBinding], 0
0x180007b05  call    cs:__imp_RpcBindingToStringBindingW
0x180007b0b  mov     ebx, eax
0x180007b0d  test    eax, eax
0x180007b0f  jnz     short loc_180007B73
0x180007b11  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x180007b16  lea     r8, [rsp+38h+Protseq]; Protseq
0x180007b1b  mov     [rsp+38h+NetworkOptions], 0; NetworkOptions
0x180007b24  xor     r9d, r9d; NetworkAddr
0x180007b27  xor     edx, edx; ObjUuid
0x180007b29  mov     [rsp+38h+Endpoint], 0; Endpoint
0x180007b32  call    cs:__imp_RpcStringBindingParseW
0x180007b38  mov     ebx, eax
0x180007b3a  test    eax, eax
0x180007b3c  jnz     short loc_180007B73
0x180007b3e  mov     rcx, [rsp+38h+Protseq]; String1
0x180007b43  lea     rdx, aNcacnNp; "ncacn_np"
0x180007b4a  call    cs:__imp__wcsicmp
0x180007b50  test    eax, eax
0x180007b52  jz      short loc_180007B71
0x180007b54  mov     rcx, [rsp+38h+Protseq]; String1
0x180007b59  lea     rdx, aNcalrpc; "ncalrpc"
0x180007b60  call    cs:__imp__wcsicmp
0x180007b66  test    eax, eax
0x180007b68  jz      short loc_180007B71
0x180007b6a  mov     ebx, 5
0x180007b6f  jmp     short loc_180007B73
0x180007b71  xor     ebx, ebx
0x180007b73  cmp     [rsp+38h+Protseq], 0
0x180007b79  jz      short loc_180007B86
0x180007b7b  lea     rcx, [rsp+38h+Protseq]; String
0x180007b80  call    cs:__imp_RpcStringFreeW
0x180007b86  cmp     [rsp+38h+StringBinding], 0
0x180007b8c  jz      short loc_180007B99
0x180007b8e  lea     rcx, [rsp+38h+StringBinding]; String
0x180007b93  call    cs:__imp_RpcStringFreeW
0x180007b99  mov     eax, ebx
0x180007b9b  add     rsp, 30h
0x180007b9f  pop     rbx
0x180007ba0  retn
```

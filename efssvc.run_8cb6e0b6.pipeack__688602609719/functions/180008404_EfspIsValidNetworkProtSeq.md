# EfspIsValidNetworkProtSeq

- ea: `0x180008404`
- end: `0x1800084e2`
- name: `EfspIsValidNetworkProtSeq`
- size: `222`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800059a0`
- `0x180005d00`
- `0x1800060c0`
- `0x1800069d0`
- `0x180006bf0`
- `0x180006d80`
- `0x1800070d0`
- `0x1800072b0`
- `0x1800080c4`

## callees

- `0x180008404`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180008472`
- `msvcrt!_wcsicmp` at `0x18000848e`
- `msvcrt!_wcsicmp` at `0x180008472`
- `msvcrt!_wcsicmp` at `0x18000848e`
- `RPCRT4!RpcStringBindingParseW` at `0x180008454`
- `RPCRT4!RpcStringBindingParseW` at `0x180008454`
- `RPCRT4!RpcStringFreeW` at `0x1800084b4`
- `RPCRT4!RpcStringFreeW` at `0x1800084cd`
- `RPCRT4!RpcStringFreeW` at `0x1800084b4`
- `RPCRT4!RpcStringFreeW` at `0x1800084cd`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180008421`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180008421`

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
0x180008404  push    rbx
0x180008406  sub     rsp, 30h
0x18000840a  lea     rdx, [rsp+38h+StringBinding]; StringBinding
0x18000840f  mov     [rsp+38h+Protseq], 0
0x180008418  mov     [rsp+38h+StringBinding], 0
0x180008421  call    cs:__imp_RpcBindingToStringBindingW
0x180008428  nop     dword ptr [rax+rax+00h]
0x18000842d  mov     ebx, eax
0x18000842f  test    eax, eax
0x180008431  jnz     short loc_1800084A7
0x180008433  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x180008438  lea     r8, [rsp+38h+Protseq]; Protseq
0x18000843d  mov     [rsp+38h+NetworkOptions], 0; NetworkOptions
0x180008446  xor     r9d, r9d; NetworkAddr
0x180008449  xor     edx, edx; ObjUuid
0x18000844b  mov     [rsp+38h+Endpoint], 0; Endpoint
0x180008454  call    cs:__imp_RpcStringBindingParseW
0x18000845b  nop     dword ptr [rax+rax+00h]
0x180008460  mov     ebx, eax
0x180008462  test    eax, eax
0x180008464  jnz     short loc_1800084A7
0x180008466  mov     rcx, [rsp+38h+Protseq]; String1
0x18000846b  lea     rdx, aNcacnNp; "ncacn_np"
0x180008472  call    cs:__imp__wcsicmp
0x180008479  nop     dword ptr [rax+rax+00h]
0x18000847e  test    eax, eax
0x180008480  jz      short loc_1800084A5
0x180008482  mov     rcx, [rsp+38h+Protseq]; String1
0x180008487  lea     rdx, aNcalrpc; "ncalrpc"
0x18000848e  call    cs:__imp__wcsicmp
0x180008495  nop     dword ptr [rax+rax+00h]
0x18000849a  test    eax, eax
0x18000849c  jz      short loc_1800084A5
0x18000849e  mov     ebx, 5
0x1800084a3  jmp     short loc_1800084A7
0x1800084a5  xor     ebx, ebx
0x1800084a7  cmp     [rsp+38h+Protseq], 0
0x1800084ad  jz      short loc_1800084C0
0x1800084af  lea     rcx, [rsp+38h+Protseq]; String
0x1800084b4  call    cs:__imp_RpcStringFreeW
0x1800084bb  nop     dword ptr [rax+rax+00h]
0x1800084c0  cmp     [rsp+38h+StringBinding], 0
0x1800084c6  jz      short loc_1800084D9
0x1800084c8  lea     rcx, [rsp+38h+StringBinding]; String
0x1800084cd  call    cs:__imp_RpcStringFreeW
0x1800084d4  nop     dword ptr [rax+rax+00h]
0x1800084d9  mov     eax, ebx
0x1800084db  add     rsp, 30h
0x1800084df  pop     rbx
0x1800084e0  retn
```

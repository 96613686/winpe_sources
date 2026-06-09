# DSCRemoveExpiredTokens(void)

- ea: `0x180001500`
- end: `0x18000158f`
- name: `?DSCRemoveExpiredTokens@@YAJXZ`
- size: `143`
- prototype: `CLIENT_CALL_RETURN(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002060`

## callees

- `0x180001500`
- `0x180001cf0`
- `0x180002220`
- `0x180006d94`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180009a9e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180009a9e`
- `RPCRT4!NdrClientCall3` at `0x180001540`
- `RPCRT4!NdrClientCall3` at `0x180001540`

## pseudocode

```c
CLIENT_CALL_RETURN DSCRemoveExpiredTokens(void)
{
  RpcBinding *v0; // rbx
  CLIENT_CALL_RETURN result; // rax

  v0 = (RpcBinding *)tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get();
  result.Simple = RpcBinding::Bind(v0);
  if ( SLODWORD(result.Simple) >= 0 )
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 7u, 0, *(_QWORD *)v0);
  return result;
}

```

## disassembly

```asm
0x180001500  push    rbx
0x180001502  sub     rsp, 20h
0x180001506  call    ?get@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAAAEAVAutoRpcBinding@@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get(void)
0x18000150b  mov     rbx, rax
0x18000150e  mov     [rsp+28h+arg_18], rax
0x180001513  mov     rcx, rax; this
0x180001516  call    ?Bind@RpcBinding@@QEAAJXZ; RpcBinding::Bind(void)
0x18000151b  test    eax, eax
0x18000151d  js      short loc_180001589
0x18000151f  mov     [rsp+28h+arg_0], 0
0x180001524  nop
0x180001525  mov     [rsp+28h+arg_10], 0
0x18000152e  mov     r9, [rbx]
0x180001531  xor     r8d, r8d; pReturnValue
0x180001534  mov     edx, 7; nProcNum
0x180001539  lea     rcx, pProxyInfo; pProxyInfo
0x180001540  call    cs:__imp_NdrClientCall3
0x180001546  mov     [rsp+28h+arg_10], rax
0x18000154b  mov     [rsp+28h+arg_8], eax
0x18000154f  jmp     short loc_180001589
0x180001551  test    eax, eax
0x180001553  jle     short loc_18000155D
0x180001555  movzx   eax, ax
0x180001558  or      eax, 80070000h
0x18000155d  mov     ecx, 8000FFFFh
0x180001562  test    eax, eax
0x180001564  cmovns  eax, ecx
0x180001567  cmp     [rsp+28h+arg_0], 0
0x18000156c  jnz     short loc_180001589
0x18000156e  cmp     eax, 800706BFh
0x180001573  jnz     short loc_180001589
0x180001575  mov     rbx, [rsp+28h+arg_18]
0x18000157a  mov     rcx, rbx; this
0x18000157d  call    ?Rebind@RpcBinding@@QEAAJXZ; RpcBinding::Rebind(void)
0x180001582  mov     [rsp+28h+arg_0], 1
0x180001587  jmp     short loc_180001524
0x180001589  add     rsp, 20h
0x18000158d  pop     rbx
0x18000158e  retn
0x180009a90  push    rbp
0x180009a92  sub     rsp, 20h
0x180009a96  mov     rbp, rdx
0x180009a99  mov     rcx, [rcx]
0x180009a9c  mov     ecx, [rcx]; ExceptionCode
0x180009a9e  call    cs:__imp_I_RpcExceptionFilter
0x180009aa4  nop
0x180009aa5  add     rsp, 20h
0x180009aa9  pop     rbp
0x180009aaa  retn
```

# DSCDelegateSharingToken(ushort const *,_DS_SHARE_SCOPE *)

- ea: `0x180003a7c`
- end: `0x180003b31`
- name: `?DSCDelegateSharingToken@@YAJPEBGPEAU_DS_SHARE_SCOPE@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _DS_SHARE_SCOPE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800032a0`

## callees

- `0x180001cf0`
- `0x180002220`
- `0x180003a7c`
- `0x180006d94`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180003ad6`
- `RPCRT4!NdrClientCall3` at `0x180003ad6`

## pseudocode

```c
__int64 __fastcall DSCDelegateSharingToken(const unsigned __int16 *a1, struct _DS_SHARE_SCOPE *a2)
{
  RPC_BINDING_HANDLE *v4; // rbx
  __int64 result; // rax

  v4 = (RPC_BINDING_HANDLE *)tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get();
  result = RpcBinding::Bind(v4);
  if ( (int)result >= 0 )
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0, *v4, a1, a2, 0, v4).Simple;
  return result;
}

```

## disassembly

```asm
0x180003a7c  mov     [rsp+arg_8], rdx
0x180003a81  mov     [rsp+arg_0], rcx
0x180003a86  push    rbx
0x180003a87  push    rsi
0x180003a88  push    rdi
0x180003a89  sub     rsp, 40h
0x180003a8d  mov     rdi, rdx
0x180003a90  mov     rsi, rcx
0x180003a93  call    ?get@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAAAEAVAutoRpcBinding@@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get(void)
0x180003a98  mov     rbx, rax
0x180003a9b  mov     [rsp+58h+var_20], rax
0x180003aa0  mov     rcx, rax; this
0x180003aa3  call    ?Bind@RpcBinding@@QEAAJXZ; RpcBinding::Bind(void)
0x180003aa8  test    eax, eax
0x180003aaa  js      short loc_180003B29
0x180003aac  mov     [rsp+58h+arg_10], 0
0x180003ab1  nop
0x180003ab2  mov     [rsp+58h+var_28], 0
0x180003abb  mov     [rsp+58h+var_30], rdi
0x180003ac0  mov     [rsp+58h+var_38], rsi
0x180003ac5  mov     r9, [rbx]
0x180003ac8  xor     r8d, r8d; pReturnValue
0x180003acb  lea     edx, [r8+3]; nProcNum
0x180003acf  lea     rcx, pProxyInfo; pProxyInfo
0x180003ad6  call    cs:__imp_NdrClientCall3
0x180003adc  mov     [rsp+58h+var_28], rax
0x180003ae1  mov     [rsp+58h+arg_18], eax
0x180003ae5  jmp     short loc_180003B29
0x180003ae7  test    eax, eax
0x180003ae9  jle     short loc_180003AF3
0x180003aeb  movzx   eax, ax
0x180003aee  or      eax, 80070000h
0x180003af3  mov     ecx, 8000FFFFh
0x180003af8  test    eax, eax
0x180003afa  cmovns  eax, ecx
0x180003afd  cmp     [rsp+58h+arg_10], 0
0x180003b02  jnz     short loc_180003B29
0x180003b04  cmp     eax, 800706BFh
0x180003b09  jnz     short loc_180003B29
0x180003b0b  mov     rbx, [rsp+58h+var_20]
0x180003b10  mov     rcx, rbx; this
0x180003b13  call    ?Rebind@RpcBinding@@QEAAJXZ; RpcBinding::Rebind(void)
0x180003b18  mov     [rsp+58h+arg_10], 1
0x180003b1d  mov     rdi, [rsp+58h+arg_8]
0x180003b22  mov     rsi, [rsp+58h+arg_0]
0x180003b27  jmp     short loc_180003AB1
0x180003b29  add     rsp, 40h
0x180003b2d  pop     rdi
0x180003b2e  pop     rsi
0x180003b2f  pop     rbx
0x180003b30  retn
0x180009de7  push    rbp
0x180009de9  sub     rsp, 30h
0x180009ded  mov     rbp, rdx
0x180009df0  mov     rcx, [rcx]
0x180009df3  mov     ecx, [rcx]; ExceptionCode
0x180009df5  call    cs:__imp_I_RpcExceptionFilter
0x180009dfb  nop
0x180009dfc  add     rsp, 30h
0x180009e00  pop     rbp
0x180009e01  retn
```

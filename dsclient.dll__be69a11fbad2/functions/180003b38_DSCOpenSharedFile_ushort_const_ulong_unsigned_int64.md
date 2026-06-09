# DSCOpenSharedFile(ushort const *,ulong,unsigned __int64 *)

- ea: `0x180003b38`
- end: `0x180003c18`
- name: `?DSCOpenSharedFile@@YAJPEBGKPEA_K@Z`
- size: `224`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003380`

## callees

- `0x180001cf0`
- `0x180002220`
- `0x180003b38`
- `0x180006d94`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180009e17`
- `RPCRT4!I_RpcExceptionFilter` at `0x180009e17`
- `RPCRT4!NdrClientCall3` at `0x180003ba5`
- `RPCRT4!NdrClientCall3` at `0x180003ba5`

## pseudocode

```c
__int64 __fastcall DSCOpenSharedFile(const unsigned __int16 *a1, int a2, unsigned __int64 *a3)
{
  RPC_BINDING_HANDLE *v6; // rbx
  __int64 result; // rax
  int v8; // [rsp+28h] [rbp-60h]

  v6 = (RPC_BINDING_HANDLE *)tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get();
  result = RpcBinding::Bind(v6);
  if ( (int)result >= 0 )
  {
    v8 = a2;
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 5u, 0, *v6, a1, v8, a3).Simple;
  }
  return result;
}

```

## disassembly

```asm
0x180003b38  mov     [rsp+arg_10], r8
0x180003b3d  mov     [rsp+arg_8], edx
0x180003b41  mov     [rsp+arg_0], rcx
0x180003b46  push    rbx
0x180003b47  push    rsi
0x180003b48  push    rdi
0x180003b49  push    r14
0x180003b4b  sub     rsp, 68h
0x180003b4f  mov     rdi, r8
0x180003b52  mov     esi, edx
0x180003b54  mov     r14, rcx
0x180003b57  call    ?get@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAAAEAVAutoRpcBinding@@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::get(void)
0x180003b5c  mov     rbx, rax
0x180003b5f  mov     [rsp+88h+var_38], rax
0x180003b64  mov     rcx, rax; this
0x180003b67  call    ?Bind@RpcBinding@@QEAAJXZ; RpcBinding::Bind(void)
0x180003b6c  test    eax, eax
0x180003b6e  js      loc_180003C0E
0x180003b74  mov     [rsp+88h+arg_18], 0
0x180003b7c  nop
0x180003b7d  mov     [rsp+88h+var_40], 0
0x180003b86  mov     [rsp+88h+var_58], rdi
0x180003b8b  mov     [rsp+88h+var_60], esi
0x180003b8f  mov     [rsp+88h+var_68], r14
0x180003b94  mov     r9, [rbx]
0x180003b97  xor     r8d, r8d; pReturnValue
0x180003b9a  lea     edx, [r8+5]; nProcNum
0x180003b9e  lea     rcx, pProxyInfo; pProxyInfo
0x180003ba5  call    cs:__imp_NdrClientCall3
0x180003bab  mov     [rsp+88h+var_40], rax
0x180003bb0  mov     [rsp+88h+var_48], eax
0x180003bb4  jmp     short loc_180003C0E
0x180003bb6  test    eax, eax
0x180003bb8  jle     short loc_180003BC2
0x180003bba  movzx   eax, ax
0x180003bbd  or      eax, 80070000h
0x180003bc2  mov     ecx, 8000FFFFh
0x180003bc7  test    eax, eax
0x180003bc9  cmovns  eax, ecx
0x180003bcc  cmp     [rsp+88h+arg_18], 0
0x180003bd4  jnz     short loc_180003C0E
0x180003bd6  cmp     eax, 800706BFh
0x180003bdb  jnz     short loc_180003C0E
0x180003bdd  mov     rbx, [rsp+88h+var_38]
0x180003be2  mov     rcx, rbx; this
0x180003be5  call    ?Rebind@RpcBinding@@QEAAJXZ; RpcBinding::Rebind(void)
0x180003bea  mov     [rsp+88h+arg_18], 1
0x180003bf2  mov     rdi, [rsp+88h+arg_10]
0x180003bfa  mov     esi, [rsp+88h+arg_8]
0x180003c01  mov     r14, [rsp+88h+arg_0]
0x180003c09  jmp     loc_180003B7C
0x180003c0e  add     rsp, 68h
0x180003c12  pop     r14
0x180003c14  pop     rdi
0x180003c15  pop     rsi
0x180003c16  pop     rbx
0x180003c17  retn
0x180009e09  push    rbp
0x180009e0b  sub     rsp, 40h
0x180009e0f  mov     rbp, rdx
0x180009e12  mov     rcx, [rcx]
0x180009e15  mov     ecx, [rcx]; ExceptionCode
0x180009e17  call    cs:__imp_I_RpcExceptionFilter
0x180009e1d  nop
0x180009e1e  add     rsp, 40h
0x180009e22  pop     rbp
0x180009e23  retn
```

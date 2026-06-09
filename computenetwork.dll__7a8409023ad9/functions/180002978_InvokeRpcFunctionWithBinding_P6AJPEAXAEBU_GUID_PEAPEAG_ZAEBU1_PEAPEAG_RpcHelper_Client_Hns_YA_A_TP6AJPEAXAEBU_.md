# ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAG@ZAEBU1@PEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAG@Z1$$QEAPEAPEAG@Z

- ea: `0x180002978`
- end: `0x180002a00`
- name: `??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAG@ZAEBU1@PEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAG@Z1$$QEAPEAPEAG@Z`
- size: `136`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180005720`
- `0x1800081d0`
- `0x180008260`
- `0x1800082f0`
- `0x180008380`
- `0x180008410`

## callees

- `0x1800028bc`
- `0x180002978`
- `0x18000b8c4`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short * *),_GUID const &,unsigned short * *>()
{
  Rpc::RpcClient **RpcClient; // rax
  unsigned int v1; // edi
  volatile signed __int32 *v2; // rbx
  __int64 v4; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v5; // [rsp+28h] [rbp-10h]

  RpcClient = (Rpc::RpcClient **)Hns::Client::RpcHelper::GetRpcClient(&v4);
  v1 = Rpc::RpcClient::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short * *),_GUID const &,unsigned short * *>(*RpcClient);
  v2 = v5;
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180002978  mov     [rsp+arg_0], rbx
0x18000297d  mov     [rsp+arg_8], rsi
0x180002982  push    rdi
0x180002983  sub     rsp, 30h
0x180002987  mov     rbx, r8
0x18000298a  mov     rdi, rdx
0x18000298d  mov     rsi, rcx
0x180002990  lea     rcx, [rsp+38h+var_18]
0x180002995  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x18000299a  nop
0x18000299b  mov     r9, rbx
0x18000299e  mov     r8, rdi
0x1800029a1  mov     rdx, rsi
0x1800029a4  mov     rcx, [rax]; this
0x1800029a7  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAG@ZAEBU1@PEAPEAG@RpcClient@Rpc@@QEAA?A_TP6AJPEAXAEBU_GUID@@PEAPEAG@Z1$$QEAPEAPEAG@Z
0x1800029ac  mov     edi, eax
0x1800029ae  mov     rbx, [rsp+38h+var_10]
0x1800029b3  test    rbx, rbx
0x1800029b6  jz      short loc_1800029EE
0x1800029b8  or      esi, 0FFFFFFFFh
0x1800029bb  mov     ecx, esi
0x1800029bd  lock xadd [rbx+8], ecx
0x1800029c2  add     ecx, esi
0x1800029c4  jnz     short loc_1800029EE
0x1800029c6  mov     rdx, [rbx]
0x1800029c9  mov     rcx, rbx
0x1800029cc  mov     rax, [rdx]
0x1800029cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d4  mov     eax, esi
0x1800029d6  lock xadd [rbx+0Ch], eax
0x1800029db  add     eax, esi
0x1800029dd  jnz     short loc_1800029EE
0x1800029df  mov     rax, [rbx]
0x1800029e2  mov     rcx, rbx
0x1800029e5  mov     rax, [rax+8]
0x1800029e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ee  mov     eax, edi
0x1800029f0  mov     rbx, [rsp+38h+arg_0]
0x1800029f5  mov     rsi, [rsp+38h+arg_8]
0x1800029fa  add     rsp, 30h
0x1800029fe  pop     rdi
0x1800029ff  retn
```

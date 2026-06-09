# ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z

- ea: `0x180002f88`
- end: `0x18000300b`
- name: `??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z`
- size: `131`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x1800057b0`
- `0x180005870`
- `0x180005c70`
- `0x1800084a0`
- `0x180008670`
- `0x180008730`
- `0x1800087f0`

## callees

- `0x180002ebc`
- `0x180002f88`
- `0x18000b8c4`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),unsigned short const * &,unsigned short * * &,unsigned short * *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  Rpc::RpcClient **RpcClient; // rax
  unsigned int v6; // edi
  volatile signed __int32 *v7; // rbx
  __int64 v9; // [rsp+30h] [rbp-38h] BYREF
  volatile signed __int32 *v10; // [rsp+38h] [rbp-30h]

  RpcClient = (Rpc::RpcClient **)Hns::Client::RpcHelper::GetRpcClient(&v9);
  v6 = Rpc::RpcClient::InvokeRpcFunctionWithBinding<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),unsigned short const * &,unsigned short * * &,unsigned short * *>(
         *RpcClient,
         a4);
  v7 = v10;
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180002f88  push    rbx
0x180002f8a  push    rbp
0x180002f8b  push    rsi
0x180002f8c  push    rdi
0x180002f8d  sub     rsp, 48h
0x180002f91  mov     rbx, r9
0x180002f94  mov     rdi, r8
0x180002f97  mov     rsi, rdx
0x180002f9a  mov     rbp, rcx
0x180002f9d  lea     rcx, [rsp+68h+var_38]
0x180002fa2  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x180002fa7  nop
0x180002fa8  mov     [rsp+68h+var_48], rbx; __int64
0x180002fad  mov     r9, rdi
0x180002fb0  mov     r8, rsi
0x180002fb3  mov     rdx, rbp
0x180002fb6  mov     rcx, [rax]; this
0x180002fb9  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcClient@Rpc@@QEAA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180002fbe  mov     edi, eax
0x180002fc0  mov     rbx, [rsp+68h+var_30]
0x180002fc5  test    rbx, rbx
0x180002fc8  jz      short loc_180003000
0x180002fca  or      esi, 0FFFFFFFFh
0x180002fcd  mov     ecx, esi
0x180002fcf  lock xadd [rbx+8], ecx
0x180002fd4  add     ecx, esi
0x180002fd6  jnz     short loc_180003000
0x180002fd8  mov     rdx, [rbx]
0x180002fdb  mov     rcx, rbx
0x180002fde  mov     rax, [rdx]
0x180002fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe6  mov     eax, esi
0x180002fe8  lock xadd [rbx+0Ch], eax
0x180002fed  add     eax, esi
0x180002fef  jnz     short loc_180003000
0x180002ff1  mov     rax, [rbx]
0x180002ff4  mov     rcx, rbx
0x180002ff7  mov     rax, [rax+8]
0x180002ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003000  mov     eax, edi
0x180003002  add     rsp, 48h
0x180003006  pop     rdi
0x180003007  pop     rsi
0x180003008  pop     rbp
0x180003009  pop     rbx
0x18000300a  retn
```

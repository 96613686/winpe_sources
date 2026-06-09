# ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEBU1@AEAPEBGAEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@Z1AEAPEBGAEAPEAPEAX$$QEAPEAPEAG@Z

- ea: `0x180002c38`
- end: `0x180002cc8`
- name: `??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEBU1@AEAPEBGAEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@Z1AEAPEBGAEAPEAPEAX$$QEAPEAPEAG@Z`
- size: `144`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180005650`
- `0x180007e90`
- `0x180007f60`
- `0x180008030`
- `0x180008100`

## callees

- `0x180002b60`
- `0x180002c38`
- `0x18000b8c4`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short const *,void * *,unsigned short * *),_GUID const &,unsigned short const * &,void * * &,unsigned short * *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  Rpc::RpcClient **RpcClient; // rax
  unsigned int v7; // edi
  volatile signed __int32 *v8; // rbx
  __int64 v10; // [rsp+30h] [rbp-38h] BYREF
  volatile signed __int32 *v11; // [rsp+38h] [rbp-30h]

  RpcClient = (Rpc::RpcClient **)Hns::Client::RpcHelper::GetRpcClient(&v10);
  v7 = Rpc::RpcClient::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short const *,void * *,unsigned short * *),_GUID const &,unsigned short const * &,void * * &,unsigned short * *>(
         *RpcClient,
         a4,
         a5);
  v8 = v11;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180002c38  push    rbx
0x180002c3a  push    rbp
0x180002c3b  push    rsi
0x180002c3c  push    rdi
0x180002c3d  sub     rsp, 48h
0x180002c41  mov     rbx, r9
0x180002c44  mov     rdi, r8
0x180002c47  mov     rsi, rdx
0x180002c4a  mov     rbp, rcx
0x180002c4d  lea     rcx, [rsp+68h+var_38]
0x180002c52  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x180002c57  nop
0x180002c58  mov     r10, [rsp+68h+arg_20]
0x180002c60  mov     [rsp+68h+var_40], r10; __int64
0x180002c65  mov     [rsp+68h+var_48], rbx; __int64
0x180002c6a  mov     r9, rdi
0x180002c6d  mov     r8, rsi
0x180002c70  mov     rdx, rbp
0x180002c73  mov     rcx, [rax]; this
0x180002c76  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEBU1@AEAPEBGAEAPEAPEAXPEAPEAG@RpcClient@Rpc@@QEAA?A_TP6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@Z1AEAPEBGAEAPEAPEAX$$QEAPEAPEAG@Z
0x180002c7b  mov     edi, eax
0x180002c7d  mov     rbx, [rsp+68h+var_30]
0x180002c82  test    rbx, rbx
0x180002c85  jz      short loc_180002CBD
0x180002c87  or      esi, 0FFFFFFFFh
0x180002c8a  mov     ecx, esi
0x180002c8c  lock xadd [rbx+8], ecx
0x180002c91  add     ecx, esi
0x180002c93  jnz     short loc_180002CBD
0x180002c95  mov     rdx, [rbx]
0x180002c98  mov     rcx, rbx
0x180002c9b  mov     rax, [rdx]
0x180002c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ca3  mov     eax, esi
0x180002ca5  lock xadd [rbx+0Ch], eax
0x180002caa  add     eax, esi
0x180002cac  jnz     short loc_180002CBD
0x180002cae  mov     rax, [rbx]
0x180002cb1  mov     rcx, rbx
0x180002cb4  mov     rax, [rax+8]
0x180002cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cbd  mov     eax, edi
0x180002cbf  add     rsp, 48h
0x180002cc3  pop     rdi
0x180002cc4  pop     rsi
0x180002cc5  pop     rbp
0x180002cc6  pop     rbx
0x180002cc7  retn
```

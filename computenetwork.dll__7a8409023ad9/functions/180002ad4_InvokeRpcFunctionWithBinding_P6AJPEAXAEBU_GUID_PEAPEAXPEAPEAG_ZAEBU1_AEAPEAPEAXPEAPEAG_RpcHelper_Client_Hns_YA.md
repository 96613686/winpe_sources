# ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@ZAEBU1@AEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@Z1AEAPEAPEAX$$QEAPEAPEAG@Z

- ea: `0x180002ad4`
- end: `0x180002b57`
- name: `??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@ZAEBU1@AEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@Z1AEAPEAPEAX$$QEAPEAPEAG@Z`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800059f0`
- `0x180005ab0`
- `0x180008c90`
- `0x180008d50`
- `0x180008e10`
- `0x180008ed0`

## callees

- `0x180002a08`
- `0x180002ad4`
- `0x18000b8c4`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,void * *,unsigned short * *),_GUID const &,void * * &,unsigned short * *>(
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
  v6 = Rpc::RpcClient::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,void * *,unsigned short * *),_GUID const &,void * * &,unsigned short * *>(
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
0x180002ad4  push    rbx
0x180002ad6  push    rbp
0x180002ad7  push    rsi
0x180002ad8  push    rdi
0x180002ad9  sub     rsp, 48h
0x180002add  mov     rbx, r9
0x180002ae0  mov     rdi, r8
0x180002ae3  mov     rsi, rdx
0x180002ae6  mov     rbp, rcx
0x180002ae9  lea     rcx, [rsp+68h+var_38]
0x180002aee  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x180002af3  nop
0x180002af4  mov     [rsp+68h+var_48], rbx; __int64
0x180002af9  mov     r9, rdi
0x180002afc  mov     r8, rsi
0x180002aff  mov     rdx, rbp
0x180002b02  mov     rcx, [rax]; this
0x180002b05  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@ZAEBU1@AEAPEAPEAXPEAPEAG@RpcClient@Rpc@@QEAA?A_TP6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@Z1AEAPEAPEAX$$QEAPEAPEAG@Z
0x180002b0a  mov     edi, eax
0x180002b0c  mov     rbx, [rsp+68h+var_30]
0x180002b11  test    rbx, rbx
0x180002b14  jz      short loc_180002B4C
0x180002b16  or      esi, 0FFFFFFFFh
0x180002b19  mov     ecx, esi
0x180002b1b  lock xadd [rbx+8], ecx
0x180002b20  add     ecx, esi
0x180002b22  jnz     short loc_180002B4C
0x180002b24  mov     rdx, [rbx]
0x180002b27  mov     rcx, rbx
0x180002b2a  mov     rax, [rdx]
0x180002b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b32  mov     eax, esi
0x180002b34  lock xadd [rbx+0Ch], eax
0x180002b39  add     eax, esi
0x180002b3b  jnz     short loc_180002B4C
0x180002b3d  mov     rax, [rbx]
0x180002b40  mov     rcx, rbx
0x180002b43  mov     rax, [rax+8]
0x180002b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b4c  mov     eax, edi
0x180002b4e  add     rsp, 48h
0x180002b52  pop     rdi
0x180002b53  pop     rsi
0x180002b54  pop     rbp
0x180002b55  pop     rbx
0x180002b56  retn
```

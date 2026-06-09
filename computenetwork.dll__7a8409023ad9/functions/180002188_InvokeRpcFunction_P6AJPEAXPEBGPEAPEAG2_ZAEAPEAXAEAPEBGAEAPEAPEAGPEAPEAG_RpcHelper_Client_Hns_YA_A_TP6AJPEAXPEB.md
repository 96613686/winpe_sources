# ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z

- ea: `0x180002188`
- end: `0x18000224c`
- name: `??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z`
- size: `196`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180005b70`
- `0x180005d30`
- `0x180008f90`
- `0x180009090`
- `0x180009190`
- `0x180009390`
- `0x180009490`
- `0x180009590`
- `0x18000a40c`

## callees

- `0x180002188`
- `0x180002728`
- `0x18000b8c4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800021f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800021f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800021bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800021bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),void * &,unsigned short const * &,unsigned short * * &,unsigned short * *>(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  RTL_SRWLOCK *v9; // r14
  int v10; // ecx
  unsigned int v11; // edi
  volatile signed __int32 *v12; // rbx
  __int64 v14; // [rsp+30h] [rbp-28h] BYREF
  volatile signed __int32 *v15; // [rsp+38h] [rbp-20h]

  v9 = (RTL_SRWLOCK *)(*Hns::Client::RpcHelper::GetRpcClient(&v14) + 8LL);
  AcquireSRWLockShared(v9);
  v11 = Rpc::RpcClient::InvokeRpcFunctionInternal<long (*)(void *,unsigned long *,long *,unsigned short * *),void * &,unsigned long *,long *,unsigned short * *>(
          v10,
          a1,
          a2,
          a3,
          a4,
          a5);
  if ( v9 )
    ReleaseSRWLockShared(v9);
  v12 = v15;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180002188  mov     [rsp+arg_0], rbx
0x18000218d  mov     [rsp+arg_10], rbp
0x180002192  push    rsi
0x180002193  push    rdi
0x180002194  push    r14
0x180002196  sub     rsp, 40h
0x18000219a  mov     rbx, r9
0x18000219d  mov     rdi, r8
0x1800021a0  mov     rsi, rdx
0x1800021a3  mov     rbp, rcx
0x1800021a6  lea     rcx, [rsp+58h+var_28]
0x1800021ab  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x1800021b0  nop
0x1800021b1  mov     r14, [rax]
0x1800021b4  add     r14, 8
0x1800021b8  mov     rcx, r14; SRWLock
0x1800021bb  call    cs:__imp_AcquireSRWLockShared
0x1800021c1  mov     [rsp+58h+arg_8], r14
0x1800021c6  mov     rax, [rsp+58h+arg_20]
0x1800021ce  mov     [rsp+58h+var_30], rax
0x1800021d3  mov     [rsp+58h+var_38], rbx
0x1800021d8  mov     r9, rdi
0x1800021db  mov     r8, rsi
0x1800021de  mov     rdx, rbp
0x1800021e1  call    ??$InvokeRpcFunctionInternal@P6AJPEAXPEAKPEAJPEAPEAG@ZAEAPEAXPEAKPEAJPEAPEAG@RpcClient@Rpc@@AEAA?A_TP6AJPEAXPEAKPEAJPEAPEAG@ZAEAPEAX$$QEAPEAK$$QEAPEAJ$$QEAPEAPEAG@Z
0x1800021e6  mov     edi, eax
0x1800021e8  test    r14, r14
0x1800021eb  jz      short loc_1800021F7
0x1800021ed  mov     rcx, r14; SRWLock
0x1800021f0  call    cs:__imp_ReleaseSRWLockShared
0x1800021f6  nop
0x1800021f7  mov     rbx, [rsp+58h+var_20]
0x1800021fc  test    rbx, rbx
0x1800021ff  jz      short loc_180002237
0x180002201  or      esi, 0FFFFFFFFh
0x180002204  mov     eax, esi
0x180002206  lock xadd [rbx+8], eax
0x18000220b  add     eax, esi
0x18000220d  jnz     short loc_180002237
0x18000220f  mov     rax, [rbx]
0x180002212  mov     rcx, rbx
0x180002215  mov     rax, [rax]
0x180002218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000221d  mov     eax, esi
0x18000221f  lock xadd [rbx+0Ch], eax
0x180002224  add     eax, esi
0x180002226  jnz     short loc_180002237
0x180002228  mov     rax, [rbx]
0x18000222b  mov     rcx, rbx
0x18000222e  mov     rax, [rax+8]
0x180002232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002237  mov     eax, edi
0x180002239  mov     rbx, [rsp+58h+arg_0]
0x18000223e  mov     rbp, [rsp+58h+arg_10]
0x180002243  add     rsp, 40h
0x180002247  pop     r14
0x180002249  pop     rdi
0x18000224a  pop     rsi
0x18000224b  retn
```

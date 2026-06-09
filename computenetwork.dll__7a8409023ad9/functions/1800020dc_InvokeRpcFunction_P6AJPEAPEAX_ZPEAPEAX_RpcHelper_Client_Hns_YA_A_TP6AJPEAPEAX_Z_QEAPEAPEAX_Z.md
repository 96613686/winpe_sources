# ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z

- ea: `0x1800020dc`
- end: `0x18000217f`
- name: `??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z`
- size: `163`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x1800055f0`
- `0x180007b20`
- `0x180007b80`
- `0x180007be0`
- `0x180007c40`
- `0x180007ca0`
- `0x180009890`
- `0x180009c20`
- `0x18000a190`
- `0x18000aaa0`

## callees

- `0x1800020dc`
- `0x1800023e8`
- `0x18000b8c4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002126`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002126`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002106`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002106`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(__int64 a1, __int64 a2)
{
  RTL_SRWLOCK *v4; // rsi
  __int64 v5; // rcx
  unsigned int v6; // edi
  volatile signed __int32 *v7; // rbx
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v10; // [rsp+28h] [rbp-10h]

  v4 = (RTL_SRWLOCK *)(*Hns::Client::RpcHelper::GetRpcClient(&v9) + 8LL);
  AcquireSRWLockShared(v4);
  v6 = Rpc::RpcClient::InvokeRpcFunctionInternal<long (*)(void * *),void * *>(v5, a1, a2);
  if ( v4 )
    ReleaseSRWLockShared(v4);
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
0x1800020dc  mov     [rsp+arg_0], rbx
0x1800020e1  mov     [rsp+arg_10], rsi
0x1800020e6  push    rdi
0x1800020e7  sub     rsp, 30h
0x1800020eb  mov     rbx, rdx
0x1800020ee  mov     rdi, rcx
0x1800020f1  lea     rcx, [rsp+38h+var_18]
0x1800020f6  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x1800020fb  nop
0x1800020fc  mov     rsi, [rax]
0x1800020ff  add     rsi, 8
0x180002103  mov     rcx, rsi; SRWLock
0x180002106  call    cs:__imp_AcquireSRWLockShared
0x18000210c  mov     [rsp+38h+arg_8], rsi
0x180002111  mov     r8, rbx
0x180002114  mov     rdx, rdi
0x180002117  call    ??$InvokeRpcFunctionInternal@P6AJPEAPEAX@ZPEAPEAX@RpcClient@Rpc@@AEAA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x18000211c  mov     edi, eax
0x18000211e  test    rsi, rsi
0x180002121  jz      short loc_18000212D
0x180002123  mov     rcx, rsi; SRWLock
0x180002126  call    cs:__imp_ReleaseSRWLockShared
0x18000212c  nop
0x18000212d  mov     rbx, [rsp+38h+var_10]
0x180002132  test    rbx, rbx
0x180002135  jz      short loc_18000216D
0x180002137  or      esi, 0FFFFFFFFh
0x18000213a  mov     eax, esi
0x18000213c  lock xadd [rbx+8], eax
0x180002141  add     eax, esi
0x180002143  jnz     short loc_18000216D
0x180002145  mov     rax, [rbx]
0x180002148  mov     rcx, rbx
0x18000214b  mov     rax, [rax]
0x18000214e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002153  mov     eax, esi
0x180002155  lock xadd [rbx+0Ch], eax
0x18000215a  add     eax, esi
0x18000215c  jnz     short loc_18000216D
0x18000215e  mov     rax, [rbx]
0x180002161  mov     rcx, rbx
0x180002164  mov     rax, [rax+8]
0x180002168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000216d  mov     eax, edi
0x18000216f  mov     rbx, [rsp+38h+arg_0]
0x180002174  mov     rsi, [rsp+38h+arg_10]
0x180002179  add     rsp, 30h
0x18000217d  pop     rdi
0x18000217e  retn
```

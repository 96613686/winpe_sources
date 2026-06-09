# ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z

- ea: `0x180002254`
- end: `0x18000230b`
- name: `??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180005930`
- `0x1800088d0`
- `0x180008990`
- `0x180008a50`
- `0x180008b10`
- `0x180008bd0`

## callees

- `0x180002254`
- `0x1800027a8`
- `0x18000b8c4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800022af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800022af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002287`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002287`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *),void * &,unsigned short const * &,unsigned short * *>(
        int a1,
        int a2,
        int a3,
        __int64 a4)
{
  RTL_SRWLOCK *v8; // r14
  int v9; // ecx
  unsigned int v10; // edi
  volatile signed __int32 *v11; // rbx
  __int64 v13; // [rsp+30h] [rbp-28h] BYREF
  volatile signed __int32 *v14; // [rsp+38h] [rbp-20h]

  v8 = (RTL_SRWLOCK *)(*Hns::Client::RpcHelper::GetRpcClient(&v13) + 8LL);
  AcquireSRWLockShared(v8);
  v10 = Rpc::RpcClient::InvokeRpcFunctionInternal<long (*)(void *,unsigned short const *,unsigned short * *),void * &,unsigned short const * &,unsigned short * *>(
          v9,
          a1,
          a2,
          a3,
          a4);
  if ( v8 )
    ReleaseSRWLockShared(v8);
  v11 = v14;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180002254  mov     [rsp+arg_0], rbx
0x180002259  mov     [rsp+arg_10], rbp
0x18000225e  push    rsi
0x18000225f  push    rdi
0x180002260  push    r14
0x180002262  sub     rsp, 40h
0x180002266  mov     rbx, r9
0x180002269  mov     rdi, r8
0x18000226c  mov     rsi, rdx
0x18000226f  mov     rbp, rcx
0x180002272  lea     rcx, [rsp+58h+var_28]
0x180002277  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x18000227c  nop
0x18000227d  mov     r14, [rax]
0x180002280  add     r14, 8
0x180002284  mov     rcx, r14; SRWLock
0x180002287  call    cs:__imp_AcquireSRWLockShared
0x18000228d  mov     [rsp+58h+arg_8], r14
0x180002292  mov     [rsp+58h+var_38], rbx
0x180002297  mov     r9, rdi
0x18000229a  mov     r8, rsi
0x18000229d  mov     rdx, rbp
0x1800022a0  call    ??$InvokeRpcFunctionInternal@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcClient@Rpc@@AEAA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z
0x1800022a5  mov     edi, eax
0x1800022a7  test    r14, r14
0x1800022aa  jz      short loc_1800022B6
0x1800022ac  mov     rcx, r14; SRWLock
0x1800022af  call    cs:__imp_ReleaseSRWLockShared
0x1800022b5  nop
0x1800022b6  mov     rbx, [rsp+58h+var_20]
0x1800022bb  test    rbx, rbx
0x1800022be  jz      short loc_1800022F6
0x1800022c0  or      esi, 0FFFFFFFFh
0x1800022c3  mov     eax, esi
0x1800022c5  lock xadd [rbx+8], eax
0x1800022ca  add     eax, esi
0x1800022cc  jnz     short loc_1800022F6
0x1800022ce  mov     rax, [rbx]
0x1800022d1  mov     rcx, rbx
0x1800022d4  mov     rax, [rax]
0x1800022d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022dc  mov     eax, esi
0x1800022de  lock xadd [rbx+0Ch], eax
0x1800022e3  add     eax, esi
0x1800022e5  jnz     short loc_1800022F6
0x1800022e7  mov     rax, [rbx]
0x1800022ea  mov     rcx, rbx
0x1800022ed  mov     rax, [rax+8]
0x1800022f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022f6  mov     eax, edi
0x1800022f8  mov     rbx, [rsp+58h+arg_0]
0x1800022fd  mov     rbp, [rsp+58h+arg_10]
0x180002302  add     rsp, 40h
0x180002306  pop     r14
0x180002308  pop     rdi
0x180002309  pop     rsi
0x18000230a  retn
```

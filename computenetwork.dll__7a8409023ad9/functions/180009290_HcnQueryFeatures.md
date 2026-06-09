# HcnQueryFeatures

- ea: `0x180009290`
- end: `0x180009382`
- name: `HcnQueryFeatures`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002d74`
- `0x180007904`
- `0x180009290`
- `0x180009d10`
- `0x18000b8c4`
- `0x18000f010`

## string_xrefs

- `0x18000936e`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HcnQueryFeatures(_QWORD *a1, _QWORD *a2)
{
  Rpc::RpcClient *v3; // rcx
  unsigned int v4; // esi
  unsigned int v5; // r8d
  const char *v6; // r9
  volatile signed __int32 *v7; // rbx
  void *v8; // rax
  void *v9; // rcx
  __int64 result; // rax
  __int64 v11; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v12; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *v14; // [rsp+60h] [rbp+18h] BYREF
  void **v15; // [rsp+68h] [rbp+20h]

  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v11);
    *a1 = 0;
    if ( a2 )
      *a2 = 0;
    v14 = 0;
    v15 = &v14;
    v3 = (Rpc::RpcClient *)*Hns::Client::RpcHelper::GetRpcClient(&v11);
    v4 = Rpc::RpcClient::InvokeRpcFunctionWithBinding<long (*)(void *,unsigned short * *,unsigned short * *),unsigned short * * &,unsigned short * *>(v3);
    v7 = v12;
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    if ( a2 )
    {
      v8 = v14;
      v9 = 0;
      v14 = 0;
      *a2 = v8;
    }
    else
    {
      v9 = v14;
    }
    if ( v9 )
      MIDL_user_free(v9);
    result = v4;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x844, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180009290  mov     [rsp+arg_0], rcx
0x180009295  push    rbx
0x180009296  push    rsi
0x180009297  push    rdi
0x180009298  sub     rsp, 30h
0x18000929c  mov     rdi, rdx
0x18000929f  mov     rax, [rsp+48h]
0x1800092a4  test    rcx, rcx
0x1800092a7  jz      loc_180009368
0x1800092ad  mov     qword ptr [rcx], 0
0x1800092b4  test    rdi, rdi
0x1800092b7  jz      short loc_1800092C0
0x1800092b9  mov     qword ptr [rdx], 0
0x1800092c0  mov     [rsp+48h+arg_10], 0
0x1800092c9  lea     rax, [rsp+48h+arg_10]
0x1800092ce  mov     [rsp+48h+arg_18], rax
0x1800092d3  lea     rcx, [rsp+48h+var_28]
0x1800092d8  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x1800092dd  nop
0x1800092de  lea     r9, [rsp+48h+arg_18]
0x1800092e3  lea     r8, [rsp+48h+arg_0]
0x1800092e8  mov     rcx, [rax]; this
0x1800092eb  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEAPEAG1@ZAEAPEAPEAGPEAPEAG@RpcClient@Rpc@@QEAA?A_TP6AJPEAXPEAPEAG1@ZAEAPEAPEAG$$QEAPEAPEAG@Z
0x1800092f0  mov     esi, eax
0x1800092f2  mov     rbx, [rsp+48h+var_20]
0x1800092f7  test    rbx, rbx
0x1800092fa  jz      short loc_180009333
0x1800092fc  or      ecx, 0FFFFFFFFh
0x1800092ff  lock xadd [rbx+8], ecx
0x180009304  cmp     ecx, 1
0x180009307  jnz     short loc_180009333
0x180009309  mov     rax, [rbx]
0x18000930c  mov     rcx, rbx
0x18000930f  mov     rax, [rax]
0x180009312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009317  or      eax, 0FFFFFFFFh
0x18000931a  lock xadd [rbx+0Ch], eax
0x18000931f  cmp     eax, 1
0x180009322  jnz     short loc_180009333
0x180009324  mov     rax, [rbx]
0x180009327  mov     rcx, rbx
0x18000932a  mov     rax, [rax+8]
0x18000932e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009333  test    rdi, rdi
0x180009336  jz      short loc_180009349
0x180009338  mov     rax, [rsp+48h+arg_10]
0x18000933d  xor     ecx, ecx
0x18000933f  mov     [rsp+48h+arg_10], rcx
0x180009344  mov     [rdi], rax
0x180009347  jmp     short loc_18000934E
0x180009349  mov     rcx, [rsp+48h+arg_10]; void *
0x18000934e  test    rcx, rcx
0x180009351  jz      short loc_180009358
0x180009353  call    MIDL_user_free
0x180009358  mov     eax, esi
0x18000935a  jmp     short loc_180009360
0x18000935c  mov     eax, dword ptr [rsp+48h+arg_0]
0x180009360  add     rsp, 30h
0x180009364  pop     rdi
0x180009365  pop     rsi
0x180009366  pop     rbx
0x180009367  retn
0x180009368  mov     r9d, 80004003h; char *
0x18000936e  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009375  lea     edx, [rcx+10h]; void *
0x180009378  mov     rcx, rax; this
0x18000937b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

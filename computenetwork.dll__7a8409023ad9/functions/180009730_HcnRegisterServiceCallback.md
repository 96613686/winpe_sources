# HcnRegisterServiceCallback

- ea: `0x180009730`
- end: `0x180009881`
- name: `HcnRegisterServiceCallback`
- size: `337`
- prototype: `HRESULT __stdcall(HCN_NOTIFICATION_CALLBACK Callback, void *Context, HCN_CALLBACK *CallbackHandle)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002e18`
- `0x180007904`
- `0x180009730`
- `0x180009d10`
- `0x18000a608`
- `0x18000b8c4`
- `0x18000f010`

## string_xrefs

- `0x180009842`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180009859`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x18000986e`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall HcnRegisterServiceCallback(
        HCN_NOTIFICATION_CALLBACK Callback,
        void *Context,
        HCN_CALLBACK *CallbackHandle)
{
  Rpc::RpcClient *v6; // rcx
  int v7; // esi
  volatile signed __int32 *v8; // rbx
  unsigned int v9; // r8d
  const char *v10; // r9
  HRESULT result; // eax
  int v12; // [rsp+20h] [rbp-38h]
  __int64 v13; // [rsp+30h] [rbp-28h] BYREF
  volatile signed __int32 *v14; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *v16; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    if ( !Callback )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x749,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v12);
    if ( !CallbackHandle )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x74A,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80004003LL,
        v12);
    v16 = 0;
    v6 = (Rpc::RpcClient *)*Hns::Client::RpcHelper::GetRpcClient(&v13);
    v7 = Rpc::RpcClient::InvokeRpcFunctionWithBinding<long (*)(void *,void * *,unsigned short * *),void * *,unsigned short * *>(v6);
    v8 = v14;
    if ( v14 )
    {
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x752,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)(unsigned int)v7,
        (int)&v16);
    *CallbackHandle = Hns::Client::Notifications::NotificationCallbacks::RegisterCallback(
                        (RTL_SRWLOCK *)qword_180018470,
                        0,
                        (char *)Context,
                        Callback);
    if ( v16 )
      MIDL_user_free(v16);
    result = 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x757, v9, v10);
  }
  return result;
}

```

## disassembly

```asm
0x180009730  mov     [rsp+arg_8], rbx
0x180009735  mov     [rsp+arg_10], rsi
0x18000973a  push    rdi
0x18000973b  push    r14
0x18000973d  push    r15
0x18000973f  sub     rsp, 40h
0x180009743  mov     rdi, r8
0x180009746  mov     r15, rdx
0x180009749  mov     r14, rcx
0x18000974c  mov     rcx, [rsp+58h]; this
0x180009751  test    r14, r14
0x180009754  jz      loc_18000983C
0x18000975a  mov     rcx, [rsp+58h]; this
0x18000975f  test    rdi, rdi
0x180009762  jz      loc_180009853
0x180009768  mov     [rsp+58h+arg_0], 0
0x180009771  mov     [rsp+58h+arg_18], 0
0x18000977a  lea     rax, [rsp+58h+arg_18]
0x18000977f  mov     qword ptr [rsp+58h+var_38], rax; int
0x180009784  lea     rax, [rsp+58h+arg_0]
0x180009789  mov     [rsp+58h+var_30], rax
0x18000978e  lea     rcx, [rsp+58h+var_28]
0x180009793  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x180009798  nop
0x180009799  lea     r9, [rsp+58h+var_38]
0x18000979e  lea     r8, [rsp+58h+var_30]
0x1800097a3  mov     rcx, [rax]; this
0x1800097a6  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEAPEAXPEAPEAG@ZPEAPEAXPEAPEAG@RpcClient@Rpc@@QEAA?A_TP6AJPEAXPEAPEAXPEAPEAG@Z$$QEAPEAPEAX$$QEAPEAPEAG@Z
0x1800097ab  mov     esi, eax
0x1800097ad  mov     rbx, [rsp+58h+var_20]
0x1800097b2  test    rbx, rbx
0x1800097b5  jz      short loc_1800097EE
0x1800097b7  or      ecx, 0FFFFFFFFh
0x1800097ba  lock xadd [rbx+8], ecx
0x1800097bf  cmp     ecx, 1
0x1800097c2  jnz     short loc_1800097EE
0x1800097c4  mov     rax, [rbx]
0x1800097c7  mov     rcx, rbx
0x1800097ca  mov     rax, [rax]
0x1800097cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097d2  or      eax, 0FFFFFFFFh
0x1800097d5  lock xadd [rbx+0Ch], eax
0x1800097da  cmp     eax, 1
0x1800097dd  jnz     short loc_1800097EE
0x1800097df  mov     rax, [rbx]
0x1800097e2  mov     rcx, rbx
0x1800097e5  mov     rax, [rax+8]
0x1800097e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ee  mov     rcx, [rsp+58h]; this
0x1800097f3  test    esi, esi
0x1800097f5  js      short loc_18000986B
0x1800097f7  mov     r9, r14; void (*)(unsigned int, void *, int, const unsigned __int16 *)
0x1800097fa  mov     r8, r15; void *
0x1800097fd  mov     rdx, [rsp+58h+arg_0]; void *
0x180009802  lea     rcx, qword_180018470; this
0x180009809  call    ?RegisterCallback@NotificationCallbacks@Notifications@Client@Hns@@QEAAPEAXPEAX0P6AXK0JPEBG@Z@Z; Hns::Client::Notifications::NotificationCallbacks::RegisterCallback(void *,void *,void (*)(ulong,void *,long,ushort const *))
0x18000980e  mov     [rdi], rax
0x180009811  mov     rcx, [rsp+58h+arg_18]; void *
0x180009816  test    rcx, rcx
0x180009819  jz      short loc_180009820
0x18000981b  call    MIDL_user_free
0x180009820  xor     eax, eax
0x180009822  jmp     short loc_180009828
0x180009824  mov     eax, dword ptr [rsp+58h+arg_0]
0x180009828  mov     rbx, [rsp+58h+arg_8]
0x18000982d  mov     rsi, [rsp+58h+arg_10]
0x180009832  add     rsp, 40h
0x180009836  pop     r15
0x180009838  pop     r14
0x18000983a  pop     rdi
0x18000983b  retn
0x18000983c  mov     r9d, 80070057h; char *
0x180009842  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009849  mov     edx, 749h; void *
0x18000984e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009853  mov     r9d, 80004003h; char *
0x180009859  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009860  mov     edx, 74Ah; void *
0x180009865  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000986b  mov     r9d, esi; char *
0x18000986e  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009875  mov     edx, 752h; void *
0x18000987a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

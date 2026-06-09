# HcnReserveGuestNetworkServicePort

- ea: `0x180009920`
- end: `0x1800099cc`
- name: `HcnReserveGuestNetworkServicePort`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002314`
- `0x180007904`
- `0x180009920`

## string_xrefs

- `0x1800099a1`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x1800099bb`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
__int64 __fastcall HcnReserveGuestNetworkServicePort(__int64 a1, int a2, int a3, __int16 a4, _QWORD *a5)
{
  __int64 result; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  int v8; // [rsp+20h] [rbp-38h]
  int v9; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+44h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF
  __int16 v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = a4;
  v12 = a1;
  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x69C,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v8);
    if ( !a5 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v8);
    *a5 = 0;
    v9 = a3;
    v10 = a2;
    result = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,enum __MIDL_HnsRpc_0001,enum __MIDL_HnsRpc_0002,unsigned short,unsigned short,void * *),void * &,enum __MIDL_HnsRpc_0001,enum __MIDL_HnsRpc_0002,unsigned short &,unsigned short &,void * *>(
               (_DWORD)retaddr,
               (unsigned int)&v12,
               (unsigned int)&v10,
               (unsigned int)&v9,
               (__int64)&v13,
               (__int64)&v13,
               (__int64)&a5);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x6AA, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180009920  mov     [rsp+arg_18], r9w
0x180009926  mov     [rsp+arg_0], rcx
0x18000992b  sub     rsp, 58h
0x18000992f  mov     rax, [rsp+58h]
0x180009934  test    rcx, rcx
0x180009937  jz      short loc_18000999B
0x180009939  mov     rax, [rsp+58h+arg_20]
0x180009941  mov     rcx, [rsp+58h]; this
0x180009946  test    rax, rax
0x180009949  jz      short loc_1800099B5
0x18000994b  mov     qword ptr [rax], 0
0x180009952  mov     [rsp+58h+var_18], r8d
0x180009957  mov     [rsp+58h+var_14], edx
0x18000995b  lea     rax, [rsp+58h+arg_20]
0x180009963  mov     [rsp+58h+var_28], rax
0x180009968  lea     rax, [rsp+58h+arg_18]
0x18000996d  mov     [rsp+58h+var_30], rax
0x180009972  lea     rax, [rsp+58h+arg_18]
0x180009977  mov     [rsp+58h+var_38], rax
0x18000997c  lea     r9, [rsp+58h+var_18]
0x180009981  lea     r8, [rsp+58h+var_14]
0x180009986  lea     rdx, [rsp+58h+arg_0]
0x18000998b  call    ??$InvokeRpcFunction@P6AJPEAXW4__MIDL_HnsRpc_0001@@W4__MIDL_HnsRpc_0002@@GGPEAPEAX@ZAEAPEAXW41@W42@AEAGAEAGPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXW4__MIDL_HnsRpc_0001@@W4__MIDL_HnsRpc_0002@@GGPEAPEAX@ZAEAPEAX$$QEAW43@$$QEAW44@AEAG8$$QEAPEAPEAX@Z
0x180009990  jmp     short loc_180009996
0x180009992  mov     eax, dword ptr [rsp+58h+arg_0]
0x180009996  add     rsp, 58h
0x18000999a  retn
0x18000999b  mov     r9d, 80070057h; char *
0x1800099a1  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800099a8  mov     edx, 69Ch; void *
0x1800099ad  mov     rcx, rax; this
0x1800099b0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800099b5  mov     r9d, 80004003h; char *
0x1800099bb  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800099c2  lea     edx, [rax+10h]; void *
0x1800099c5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

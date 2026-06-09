# HcnCloseLoadBalancer

- ea: `0x180007be0`
- end: `0x180007c35`
- name: `HcnCloseLoadBalancer`
- size: `85`
- prototype: `HRESULT __stdcall(HCN_LOADBALANCER LoadBalancer)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020dc`
- `0x180007904`
- `0x180007be0`

## string_xrefs

- `0x180007c1f`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
HRESULT __stdcall HcnCloseLoadBalancer(HCN_LOADBALANCER LoadBalancer)
{
  HRESULT result; // eax
  unsigned int v2; // r8d
  const char *v3; // r9
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HCN_LOADBALANCER v6; // [rsp+30h] [rbp+8h] BYREF
  HCN_LOADBALANCER *v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = LoadBalancer;
  try
  {
    if ( !LoadBalancer )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x47F,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v4);
    v7 = &v6;
    result = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(HnsRpc_CloseLoadBalancer, &v7);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x487, v2, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007be0  mov     [rsp+arg_0], rcx
0x180007be5  sub     rsp, 28h
0x180007be9  mov     rax, [rsp+28h]
0x180007bee  test    rcx, rcx
0x180007bf1  jz      short loc_180007C19
0x180007bf3  lea     rax, [rsp+28h+arg_0]
0x180007bf8  mov     [rsp+28h+arg_8], rax
0x180007bfd  lea     rdx, [rsp+28h+arg_8]
0x180007c02  lea     rcx, HnsRpc_CloseLoadBalancer
0x180007c09  call    ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x180007c0e  jmp     short loc_180007C14
0x180007c10  mov     eax, dword ptr [rsp+28h+arg_0]
0x180007c14  add     rsp, 28h
0x180007c18  retn
0x180007c19  mov     r9d, 80070057h; char *
0x180007c1f  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180007c26  mov     edx, 47Fh; void *
0x180007c2b  mov     rcx, rax; this
0x180007c2e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

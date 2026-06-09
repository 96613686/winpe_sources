# HcnCloseNetwork

- ea: `0x180007ca0`
- end: `0x180007cf5`
- name: `HcnCloseNetwork`
- size: `85`
- prototype: `HRESULT __stdcall(HCN_NETWORK Network)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020dc`
- `0x180007904`
- `0x180007ca0`

## string_xrefs

- `0x180007cdf`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
HRESULT __stdcall HcnCloseNetwork(HCN_NETWORK Network)
{
  HRESULT result; // eax
  unsigned int v2; // r8d
  const char *v3; // r9
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HCN_NETWORK v6; // [rsp+30h] [rbp+8h] BYREF
  HCN_NETWORK *v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = Network;
  try
  {
    if ( !Network )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v4);
    v7 = &v6;
    result = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(HnsRpc_CloseNetwork, &v7);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x128, v2, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007ca0  mov     [rsp+arg_0], rcx
0x180007ca5  sub     rsp, 28h
0x180007ca9  mov     rax, [rsp+28h]
0x180007cae  test    rcx, rcx
0x180007cb1  jz      short loc_180007CD9
0x180007cb3  lea     rax, [rsp+28h+arg_0]
0x180007cb8  mov     [rsp+28h+arg_8], rax
0x180007cbd  lea     rdx, [rsp+28h+arg_8]
0x180007cc2  lea     rcx, HnsRpc_CloseNetwork
0x180007cc9  call    ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x180007cce  jmp     short loc_180007CD4
0x180007cd0  mov     eax, dword ptr [rsp+28h+arg_0]
0x180007cd4  add     rsp, 28h
0x180007cd8  retn
0x180007cd9  mov     r9d, 80070057h; char *
0x180007cdf  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180007ce6  mov     edx, 120h; void *
0x180007ceb  mov     rcx, rax; this
0x180007cee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

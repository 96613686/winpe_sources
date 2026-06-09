# HcnCloseEndpoint

- ea: `0x180007b20`
- end: `0x180007b75`
- name: `HcnCloseEndpoint`
- size: `85`
- prototype: `HRESULT __stdcall(HCN_ENDPOINT Endpoint)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020dc`
- `0x180007904`
- `0x180007b20`

## string_xrefs

- `0x180007b5f`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
HRESULT __stdcall HcnCloseEndpoint(HCN_ENDPOINT Endpoint)
{
  HRESULT result; // eax
  unsigned int v2; // r8d
  const char *v3; // r9
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HCN_ENDPOINT v6; // [rsp+30h] [rbp+8h] BYREF
  HCN_ENDPOINT *v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = Endpoint;
  try
  {
    if ( !Endpoint )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x37D,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v4);
    v7 = &v6;
    result = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(HnsRpc_CloseEndpoint, &v7);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x385, v2, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007b20  mov     [rsp+arg_0], rcx
0x180007b25  sub     rsp, 28h
0x180007b29  mov     rax, [rsp+28h]
0x180007b2e  test    rcx, rcx
0x180007b31  jz      short loc_180007B59
0x180007b33  lea     rax, [rsp+28h+arg_0]
0x180007b38  mov     [rsp+28h+arg_8], rax
0x180007b3d  lea     rdx, [rsp+28h+arg_8]
0x180007b42  lea     rcx, HnsRpc_CloseEndpoint
0x180007b49  call    ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x180007b4e  jmp     short loc_180007B54
0x180007b50  mov     eax, dword ptr [rsp+28h+arg_0]
0x180007b54  add     rsp, 28h
0x180007b58  retn
0x180007b59  mov     r9d, 80070057h; char *
0x180007b5f  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180007b66  mov     edx, 37Dh; void *
0x180007b6b  mov     rcx, rax; this
0x180007b6e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

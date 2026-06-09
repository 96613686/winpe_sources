# HcnCloseNamespace

- ea: `0x180007c40`
- end: `0x180007c95`
- name: `HcnCloseNamespace`
- size: `85`
- prototype: `HRESULT __stdcall(HCN_NAMESPACE Namespace)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020dc`
- `0x180007904`
- `0x180007c40`

## string_xrefs

- `0x180007c7f`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
HRESULT __stdcall HcnCloseNamespace(HCN_NAMESPACE Namespace)
{
  HRESULT result; // eax
  unsigned int v2; // r8d
  const char *v3; // r9
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HCN_NAMESPACE v6; // [rsp+30h] [rbp+8h] BYREF
  HCN_NAMESPACE *v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = Namespace;
  try
  {
    if ( !Namespace )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x222,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v4);
    v7 = &v6;
    result = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(HnsRpc_CloseNamespace, &v7);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x22A, v2, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007c40  mov     [rsp+arg_0], rcx
0x180007c45  sub     rsp, 28h
0x180007c49  mov     rax, [rsp+28h]
0x180007c4e  test    rcx, rcx
0x180007c51  jz      short loc_180007C79
0x180007c53  lea     rax, [rsp+28h+arg_0]
0x180007c58  mov     [rsp+28h+arg_8], rax
0x180007c5d  lea     rdx, [rsp+28h+arg_8]
0x180007c62  lea     rcx, HnsRpc_CloseNamespace
0x180007c69  call    ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x180007c6e  jmp     short loc_180007C74
0x180007c70  mov     eax, dword ptr [rsp+28h+arg_0]
0x180007c74  add     rsp, 28h
0x180007c78  retn
0x180007c79  mov     r9d, 80070057h; char *
0x180007c7f  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180007c86  mov     edx, 222h; void *
0x180007c8b  mov     rcx, rax; this
0x180007c8e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

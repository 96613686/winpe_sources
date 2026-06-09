# HcnCloseGuestNetworkService

- ea: `0x180007b80`
- end: `0x180007bd5`
- name: `HcnCloseGuestNetworkService`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800020dc`
- `0x180007904`
- `0x180007b80`

## string_xrefs

- `0x180007bbf`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
__int64 __fastcall HcnCloseGuestNetworkService(__int64 a1)
{
  __int64 result; // rax
  unsigned int v2; // r8d
  const char *v3; // r9
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = a1;
  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x677,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v4);
    v7 = &v6;
    result = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(
               HnsRpc_CloseGuestNetworkService,
               &v7);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x67F, v2, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007b80  mov     [rsp+arg_0], rcx
0x180007b85  sub     rsp, 28h
0x180007b89  mov     rax, [rsp+28h]
0x180007b8e  test    rcx, rcx
0x180007b91  jz      short loc_180007BB9
0x180007b93  lea     rax, [rsp+28h+arg_0]
0x180007b98  mov     [rsp+28h+arg_8], rax
0x180007b9d  lea     rdx, [rsp+28h+arg_8]
0x180007ba2  lea     rcx, HnsRpc_CloseGuestNetworkService
0x180007ba9  call    ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x180007bae  jmp     short loc_180007BB4
0x180007bb0  mov     eax, dword ptr [rsp+28h+arg_0]
0x180007bb4  add     rsp, 28h
0x180007bb8  retn
0x180007bb9  mov     r9d, 80070057h; char *
0x180007bbf  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180007bc6  mov     edx, 677h; void *
0x180007bcb  mov     rcx, rax; this
0x180007bce  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

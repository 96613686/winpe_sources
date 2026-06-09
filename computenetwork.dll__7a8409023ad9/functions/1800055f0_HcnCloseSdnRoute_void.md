# HcnCloseSdnRoute(void *)

- ea: `0x1800055f0`
- end: `0x180005645`
- name: `?HcnCloseSdnRoute@@YAJPEAX@Z`
- size: `85`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020dc`
- `0x1800055f0`
- `0x180007904`

## string_xrefs

- `0x18000562f`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
__int64 __fastcall HcnCloseSdnRoute(void *a1)
{
  __int64 result; // rax
  unsigned int v2; // r8d
  const char *v3; // r9
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v6; // [rsp+30h] [rbp+8h] BYREF
  void **v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = a1;
  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x57B,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v4);
    v7 = &v6;
    result = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(HnsRpc_CloseSdnRoute, &v7);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x583, v2, v3);
  }
  return result;
}

```

## disassembly

```asm
0x1800055f0  mov     [rsp+arg_0], rcx
0x1800055f5  sub     rsp, 28h
0x1800055f9  mov     rax, [rsp+28h]
0x1800055fe  test    rcx, rcx
0x180005601  jz      short loc_180005629
0x180005603  lea     rax, [rsp+28h+arg_0]
0x180005608  mov     [rsp+28h+arg_8], rax
0x18000560d  lea     rdx, [rsp+28h+arg_8]
0x180005612  lea     rcx, HnsRpc_CloseSdnRoute
0x180005619  call    ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x18000561e  jmp     short loc_180005624
0x180005620  mov     eax, dword ptr [rsp+28h+arg_0]
0x180005624  add     rsp, 28h
0x180005628  retn
0x180005629  mov     r9d, 80070057h; char *
0x18000562f  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005636  mov     edx, 57Bh; void *
0x18000563b  mov     rcx, rax; this
0x18000563e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

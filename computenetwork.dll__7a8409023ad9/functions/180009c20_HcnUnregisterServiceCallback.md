# HcnUnregisterServiceCallback

- ea: `0x180009c20`
- end: `0x180009cd0`
- name: `HcnUnregisterServiceCallback`
- size: `176`
- prototype: `HRESULT __stdcall(HCN_CALLBACK CallbackHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800020dc`
- `0x180007904`
- `0x180009c20`
- `0x18000ad58`

## string_xrefs

- `0x180009c8f`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180009ca9`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180009cbd`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
HRESULT __stdcall HcnUnregisterServiceCallback(HCN_CALLBACK CallbackHandle)
{
  int v1; // eax
  unsigned int v2; // r8d
  const char *v3; // r9
  HRESULT result; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v7; // [rsp+30h] [rbp+8h] BYREF
  void **v8; // [rsp+38h] [rbp+10h] BYREF

  try
  {
    if ( !CallbackHandle )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x769,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80004003LL,
        v5);
    v7 = 0;
    Hns::Client::Notifications::NotificationCallbacks::UnregisterCallback(
      (Hns::Client::Notifications::NotificationCallbacks *)qword_180018470,
      CallbackHandle,
      &v7);
    if ( !v7 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x76E,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070006LL,
        v5);
    v8 = &v7;
    v1 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(HnsRpc_CloseService, &v8);
    if ( v1 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x772,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)(unsigned int)v1,
        v5);
    result = 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x776, v2, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180009c20  sub     rsp, 28h
0x180009c24  mov     rax, [rsp+28h]
0x180009c29  test    rcx, rcx
0x180009c2c  jz      short loc_180009C89
0x180009c2e  mov     [rsp+28h+arg_0], 0
0x180009c37  lea     r8, [rsp+28h+arg_0]; void **
0x180009c3c  mov     rdx, rcx; void *
0x180009c3f  lea     rcx, qword_180018470; this
0x180009c46  call    ?UnregisterCallback@NotificationCallbacks@Notifications@Client@Hns@@QEAAXPEAXPEAPEAX@Z; Hns::Client::Notifications::NotificationCallbacks::UnregisterCallback(void *,void * *)
0x180009c4b  mov     rcx, [rsp+28h]; this
0x180009c50  cmp     [rsp+28h+arg_0], 0
0x180009c56  jz      short loc_180009CA3
0x180009c58  lea     rax, [rsp+28h+arg_0]
0x180009c5d  mov     [rsp+28h+arg_8], rax
0x180009c62  lea     rdx, [rsp+28h+arg_8]
0x180009c67  lea     rcx, HnsRpc_CloseService
0x180009c6e  call    ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x180009c73  mov     rcx, [rsp+28h]; this
0x180009c78  test    eax, eax
0x180009c7a  js      short loc_180009CBA
0x180009c7c  xor     eax, eax
0x180009c7e  jmp     short loc_180009C84
0x180009c80  mov     eax, dword ptr [rsp+28h+arg_0]
0x180009c84  add     rsp, 28h
0x180009c88  retn
0x180009c89  mov     r9d, 80004003h; char *
0x180009c8f  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009c96  mov     edx, 769h; void *
0x180009c9b  mov     rcx, rax; this
0x180009c9e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009ca3  mov     r9d, 80070006h; char *
0x180009ca9  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009cb0  mov     edx, 76Eh; void *
0x180009cb5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009cba  mov     r9d, eax; char *
0x180009cbd  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009cc4  mov     edx, 772h; void *
0x180009cc9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

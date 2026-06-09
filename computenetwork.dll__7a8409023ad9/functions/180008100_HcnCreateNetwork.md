# HcnCreateNetwork

- ea: `0x180008100`
- end: `0x1800081c1`
- name: `HcnCreateNetwork`
- size: `193`
- prototype: `HRESULT __stdcall(const GUID *const Id, PCWSTR Settings, PHCN_NETWORK Network, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002c38`
- `0x180007904`
- `0x180008100`
- `0x180009d10`

## string_xrefs

- `0x1800081ae`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnCreateNetwork(const GUID *const Id, PCWSTR Settings, PHCN_NETWORK Network, PWSTR *ErrorRecord)
{
  HRESULT v5; // edi
  unsigned int v6; // r8d
  const char *v7; // r9
  WCHAR *v8; // rdx
  void *v9; // rcx
  HRESULT result; // eax
  int v11; // [rsp+20h] [rbp-28h]
  void *v12; // [rsp+30h] [rbp-18h] BYREF
  void **v13; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PCWSTR v15; // [rsp+58h] [rbp+10h] BYREF
  PHCN_NETWORK v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = Network;
  v15 = Settings;
  try
  {
    if ( !Network )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v11);
    *Network = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v12 = 0;
    v13 = &v12;
    v5 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short const *,void * *,unsigned short * *),_GUID const &,unsigned short const * &,void * * &,unsigned short * *>(
           HnsRpc_CreateNetwork,
           Id,
           &v15,
           &v16,
           &v13);
    if ( ErrorRecord )
    {
      v8 = (WCHAR *)v12;
      v9 = 0;
      v12 = 0;
      *ErrorRecord = v8;
    }
    else
    {
      v9 = v12;
    }
    if ( v9 )
      MIDL_user_free(v9);
    result = v5;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x78, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180008100  mov     [rsp+arg_0], rbx
0x180008105  mov     [rsp+arg_10], r8
0x18000810a  mov     [rsp+arg_8], rdx
0x18000810f  push    rdi
0x180008110  sub     rsp, 40h
0x180008114  mov     rbx, r9
0x180008117  mov     rdx, rcx
0x18000811a  mov     rcx, [rsp+48h]; this
0x18000811f  test    r8, r8
0x180008122  jz      loc_1800081A8
0x180008128  mov     qword ptr [r8], 0
0x18000812f  test    rbx, rbx
0x180008132  jz      short loc_18000813B
0x180008134  mov     qword ptr [r9], 0
0x18000813b  mov     [rsp+48h+var_18], 0
0x180008144  lea     rax, [rsp+48h+var_18]
0x180008149  mov     [rsp+48h+var_10], rax
0x18000814e  lea     rax, [rsp+48h+var_10]
0x180008153  mov     qword ptr [rsp+48h+var_28], rax
0x180008158  lea     r9, [rsp+48h+arg_10]
0x18000815d  lea     r8, [rsp+48h+arg_8]
0x180008162  lea     rcx, HnsRpc_CreateNetwork
0x180008169  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEBU1@AEAPEBGAEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@Z1AEAPEBGAEAPEAPEAX$$QEAPEAPEAG@Z
0x18000816e  mov     edi, eax
0x180008170  test    rbx, rbx
0x180008173  jz      short loc_180008186
0x180008175  mov     rdx, [rsp+48h+var_18]
0x18000817a  xor     ecx, ecx
0x18000817c  mov     [rsp+48h+var_18], rcx
0x180008181  mov     [rbx], rdx
0x180008184  jmp     short loc_18000818B
0x180008186  mov     rcx, [rsp+48h+var_18]; void *
0x18000818b  test    rcx, rcx
0x18000818e  jz      short loc_180008195
0x180008190  call    MIDL_user_free
0x180008195  mov     eax, edi
0x180008197  jmp     short loc_18000819D
0x180008199  mov     eax, dword ptr [rsp+48h+arg_10]
0x18000819d  mov     rbx, [rsp+48h+arg_0]
0x1800081a2  add     rsp, 40h
0x1800081a6  pop     rdi
0x1800081a7  retn
0x1800081a8  mov     r9d, 80004003h; char *
0x1800081ae  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800081b5  mov     edx, 10h; void *
0x1800081ba  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

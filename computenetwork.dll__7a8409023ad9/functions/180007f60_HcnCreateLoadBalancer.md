# HcnCreateLoadBalancer

- ea: `0x180007f60`
- end: `0x180008021`
- name: `HcnCreateLoadBalancer`
- size: `193`
- prototype: `HRESULT __stdcall(const GUID *const Id, PCWSTR Settings, PHCN_LOADBALANCER LoadBalancer, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002c38`
- `0x180007904`
- `0x180007f60`
- `0x180009d10`

## string_xrefs

- `0x18000800e`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnCreateLoadBalancer(
        const GUID *const Id,
        PCWSTR Settings,
        PHCN_LOADBALANCER LoadBalancer,
        PWSTR *ErrorRecord)
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
  PHCN_LOADBALANCER v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = LoadBalancer;
  v15 = Settings;
  try
  {
    if ( !LoadBalancer )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v11);
    *LoadBalancer = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v12 = 0;
    v13 = &v12;
    v5 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short const *,void * *,unsigned short * *),_GUID const &,unsigned short const * &,void * * &,unsigned short * *>(
           HnsRpc_CreateLoadBalancer,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x3D7, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180007f60  mov     [rsp+arg_0], rbx
0x180007f65  mov     [rsp+arg_10], r8
0x180007f6a  mov     [rsp+arg_8], rdx
0x180007f6f  push    rdi
0x180007f70  sub     rsp, 40h
0x180007f74  mov     rbx, r9
0x180007f77  mov     rdx, rcx
0x180007f7a  mov     rcx, [rsp+48h]; this
0x180007f7f  test    r8, r8
0x180007f82  jz      loc_180008008
0x180007f88  mov     qword ptr [r8], 0
0x180007f8f  test    rbx, rbx
0x180007f92  jz      short loc_180007F9B
0x180007f94  mov     qword ptr [r9], 0
0x180007f9b  mov     [rsp+48h+var_18], 0
0x180007fa4  lea     rax, [rsp+48h+var_18]
0x180007fa9  mov     [rsp+48h+var_10], rax
0x180007fae  lea     rax, [rsp+48h+var_10]
0x180007fb3  mov     qword ptr [rsp+48h+var_28], rax
0x180007fb8  lea     r9, [rsp+48h+arg_10]
0x180007fbd  lea     r8, [rsp+48h+arg_8]
0x180007fc2  lea     rcx, HnsRpc_CreateLoadBalancer
0x180007fc9  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEBU1@AEAPEBGAEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@Z1AEAPEBGAEAPEAPEAX$$QEAPEAPEAG@Z
0x180007fce  mov     edi, eax
0x180007fd0  test    rbx, rbx
0x180007fd3  jz      short loc_180007FE6
0x180007fd5  mov     rdx, [rsp+48h+var_18]
0x180007fda  xor     ecx, ecx
0x180007fdc  mov     [rsp+48h+var_18], rcx
0x180007fe1  mov     [rbx], rdx
0x180007fe4  jmp     short loc_180007FEB
0x180007fe6  mov     rcx, [rsp+48h+var_18]; void *
0x180007feb  test    rcx, rcx
0x180007fee  jz      short loc_180007FF5
0x180007ff0  call    MIDL_user_free
0x180007ff5  mov     eax, edi
0x180007ff7  jmp     short loc_180007FFD
0x180007ff9  mov     eax, dword ptr [rsp+48h+arg_10]
0x180007ffd  mov     rbx, [rsp+48h+arg_0]
0x180008002  add     rsp, 40h
0x180008006  pop     rdi
0x180008007  retn
0x180008008  mov     r9d, 80004003h; char *
0x18000800e  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008015  mov     edx, 10h; void *
0x18000801a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

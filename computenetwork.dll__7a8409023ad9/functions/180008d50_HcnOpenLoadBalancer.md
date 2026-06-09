# HcnOpenLoadBalancer

- ea: `0x180008d50`
- end: `0x180008e01`
- name: `HcnOpenLoadBalancer`
- size: `177`
- prototype: `HRESULT __stdcall(const GUID *const Id, PHCN_LOADBALANCER LoadBalancer, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002ad4`
- `0x180007904`
- `0x180008d50`
- `0x180009d10`

## string_xrefs

- `0x180008dee`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnOpenLoadBalancer(const GUID *const Id, PHCN_LOADBALANCER LoadBalancer, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PHCN_LOADBALANCER v12; // [rsp+48h] [rbp+10h] BYREF
  void *v13; // [rsp+58h] [rbp+20h] BYREF

  v12 = LoadBalancer;
  try
  {
    if ( !LoadBalancer )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v10[0]);
    *LoadBalancer = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v13 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,void * *,unsigned short * *),_GUID const &,void * * &,unsigned short * *>(
           HnsRpc_OpenLoadBalancer,
           Id,
           &v12,
           v10,
           &v13);
    if ( ErrorRecord )
    {
      v7 = (WCHAR *)v13;
      v8 = 0;
      v13 = 0;
      *ErrorRecord = v7;
    }
    else
    {
      v8 = v13;
    }
    if ( v8 )
      MIDL_user_free(v8);
    result = v4;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x3FC, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008d50  mov     [rsp+arg_0], rbx
0x180008d55  mov     [rsp+arg_8], rdx
0x180008d5a  push    rdi
0x180008d5b  sub     rsp, 30h
0x180008d5f  mov     rbx, r8
0x180008d62  mov     rax, rcx
0x180008d65  mov     rcx, [rsp+38h]; this
0x180008d6a  test    rdx, rdx
0x180008d6d  jz      short loc_180008DE8
0x180008d6f  mov     qword ptr [rdx], 0
0x180008d76  test    rbx, rbx
0x180008d79  jz      short loc_180008D82
0x180008d7b  mov     qword ptr [r8], 0
0x180008d82  mov     [rsp+38h+arg_18], 0
0x180008d8b  lea     rcx, [rsp+38h+arg_18]
0x180008d90  mov     [rsp+38h+var_18], rcx
0x180008d95  lea     r9, [rsp+38h+var_18]
0x180008d9a  lea     r8, [rsp+38h+arg_8]
0x180008d9f  mov     rdx, rax
0x180008da2  lea     rcx, HnsRpc_OpenLoadBalancer
0x180008da9  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@ZAEBU1@AEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@Z1AEAPEAPEAX$$QEAPEAPEAG@Z
0x180008dae  mov     edi, eax
0x180008db0  test    rbx, rbx
0x180008db3  jz      short loc_180008DC6
0x180008db5  mov     rdx, [rsp+38h+arg_18]
0x180008dba  xor     ecx, ecx
0x180008dbc  mov     [rsp+38h+arg_18], rcx
0x180008dc1  mov     [rbx], rdx
0x180008dc4  jmp     short loc_180008DCB
0x180008dc6  mov     rcx, [rsp+38h+arg_18]; void *
0x180008dcb  test    rcx, rcx
0x180008dce  jz      short loc_180008DD5
0x180008dd0  call    MIDL_user_free
0x180008dd5  mov     eax, edi
0x180008dd7  jmp     short loc_180008DDD
0x180008dd9  mov     eax, dword ptr [rsp+38h+arg_8]
0x180008ddd  mov     rbx, [rsp+38h+arg_0]
0x180008de2  add     rsp, 30h
0x180008de6  pop     rdi
0x180008de7  retn
0x180008de8  mov     r9d, 80004003h; char *
0x180008dee  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008df5  mov     edx, 10h; void *
0x180008dfa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

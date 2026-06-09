# HcnQueryLoadBalancerProperties

- ea: `0x180009390`
- end: `0x18000947f`
- name: `HcnQueryLoadBalancerProperties`
- size: `239`
- prototype: `HRESULT __stdcall(HCN_LOADBALANCER LoadBalancer, PCWSTR Query, PWSTR *Properties, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002188`
- `0x180007904`
- `0x180009390`
- `0x180009d10`

## string_xrefs

- `0x180009452`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x18000946c`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnQueryLoadBalancerProperties(
        HCN_LOADBALANCER LoadBalancer,
        PCWSTR Query,
        PWSTR *Properties,
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
  HCN_LOADBALANCER v15; // [rsp+50h] [rbp+8h] BYREF
  PCWSTR v16; // [rsp+58h] [rbp+10h] BYREF
  PWSTR *v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = Properties;
  v16 = Query;
  v15 = LoadBalancer;
  try
  {
    if ( !LoadBalancer )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x43D,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v11);
    if ( ErrorRecord )
      *ErrorRecord = 0;
    if ( !Properties )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v11);
    *Properties = 0;
    v12 = 0;
    v13 = &v12;
    v5 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),void * &,unsigned short const * &,unsigned short * * &,unsigned short * *>(
           (unsigned int)HnsRpc_QueryLoadBalancerProperties,
           (unsigned int)&v15,
           (unsigned int)&v16,
           (unsigned int)&v17,
           (__int64)&v13);
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x44C, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180009390  mov     rax, rsp
0x180009393  mov     [rax+20h], rbx
0x180009397  mov     [rax+18h], r8
0x18000939b  mov     [rax+10h], rdx
0x18000939f  mov     [rax+8], rcx
0x1800093a3  push    rdi
0x1800093a4  sub     rsp, 40h
0x1800093a8  mov     rbx, r9
0x1800093ab  mov     rax, [rsp+48h]
0x1800093b0  test    rcx, rcx
0x1800093b3  jz      loc_18000944C
0x1800093b9  test    rbx, rbx
0x1800093bc  jz      short loc_1800093C5
0x1800093be  mov     qword ptr [r9], 0
0x1800093c5  mov     rcx, [rsp+48h]; this
0x1800093ca  test    r8, r8
0x1800093cd  jz      loc_180009466
0x1800093d3  mov     qword ptr [r8], 0
0x1800093da  mov     [rsp+48h+var_18], 0
0x1800093e3  lea     rax, [rsp+48h+var_18]
0x1800093e8  mov     [rsp+48h+var_10], rax
0x1800093ed  lea     rax, [rsp+48h+var_10]
0x1800093f2  mov     qword ptr [rsp+48h+var_28], rax
0x1800093f7  lea     r9, [rsp+48h+arg_10]
0x1800093fc  lea     r8, [rsp+48h+arg_8]
0x180009401  lea     rdx, [rsp+48h+arg_0]
0x180009406  lea     rcx, HnsRpc_QueryLoadBalancerProperties
0x18000940d  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180009412  mov     edi, eax
0x180009414  test    rbx, rbx
0x180009417  jz      short loc_18000942A
0x180009419  mov     rdx, [rsp+48h+var_18]
0x18000941e  xor     ecx, ecx
0x180009420  mov     [rsp+48h+var_18], rcx
0x180009425  mov     [rbx], rdx
0x180009428  jmp     short loc_18000942F
0x18000942a  mov     rcx, [rsp+48h+var_18]; void *
0x18000942f  test    rcx, rcx
0x180009432  jz      short loc_180009439
0x180009434  call    MIDL_user_free
0x180009439  mov     eax, edi
0x18000943b  jmp     short loc_180009441
0x18000943d  mov     eax, dword ptr [rsp+48h+arg_0]
0x180009441  mov     rbx, [rsp+48h+arg_18]
0x180009446  add     rsp, 40h
0x18000944a  pop     rdi
0x18000944b  retn
0x18000944c  mov     r9d, 80070057h; char *
0x180009452  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009459  mov     edx, 43Dh; void *
0x18000945e  mov     rcx, rax; this
0x180009461  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009466  mov     r9d, 80004003h; char *
0x18000946c  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009473  mov     edx, 10h; void *
0x180009478  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

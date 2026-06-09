# HcnEnumerateLoadBalancers

- ea: `0x180008670`
- end: `0x180008725`
- name: `HcnEnumerateLoadBalancers`
- size: `181`
- prototype: `HRESULT __stdcall(PCWSTR Query, PWSTR *LoadBalancer, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f88`
- `0x180007904`
- `0x180008670`
- `0x180009d10`

## string_xrefs

- `0x180008712`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnEnumerateLoadBalancers(PCWSTR Query, PWSTR *LoadBalancer, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PCWSTR v12; // [rsp+40h] [rbp+8h] BYREF
  PWSTR *v13; // [rsp+48h] [rbp+10h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = LoadBalancer;
  v12 = Query;
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
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),unsigned short const * &,unsigned short * * &,unsigned short * *>(
           HnsRpc_EnumerateLoadBalancers,
           &v12,
           &v13,
           v10,
           &v14);
    if ( ErrorRecord )
    {
      v7 = (WCHAR *)v14;
      v8 = 0;
      v14 = 0;
      *ErrorRecord = v7;
    }
    else
    {
      v8 = v14;
    }
    if ( v8 )
      MIDL_user_free(v8);
    result = v4;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x3AF, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008670  mov     [rsp+arg_10], rbx
0x180008675  mov     [rsp+arg_8], rdx
0x18000867a  mov     [rsp+arg_0], rcx
0x18000867f  push    rdi
0x180008680  sub     rsp, 30h
0x180008684  mov     rbx, r8
0x180008687  mov     rcx, [rsp+38h]; this
0x18000868c  test    rdx, rdx
0x18000868f  jz      short loc_18000870C
0x180008691  mov     qword ptr [rdx], 0
0x180008698  test    rbx, rbx
0x18000869b  jz      short loc_1800086A4
0x18000869d  mov     qword ptr [r8], 0
0x1800086a4  mov     [rsp+38h+arg_18], 0
0x1800086ad  lea     rax, [rsp+38h+arg_18]
0x1800086b2  mov     [rsp+38h+var_18], rax
0x1800086b7  lea     r9, [rsp+38h+var_18]
0x1800086bc  lea     r8, [rsp+38h+arg_8]
0x1800086c1  lea     rdx, [rsp+38h+arg_0]
0x1800086c6  lea     rcx, HnsRpc_EnumerateLoadBalancers
0x1800086cd  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x1800086d2  mov     edi, eax
0x1800086d4  test    rbx, rbx
0x1800086d7  jz      short loc_1800086EA
0x1800086d9  mov     rdx, [rsp+38h+arg_18]
0x1800086de  xor     ecx, ecx
0x1800086e0  mov     [rsp+38h+arg_18], rcx
0x1800086e5  mov     [rbx], rdx
0x1800086e8  jmp     short loc_1800086EF
0x1800086ea  mov     rcx, [rsp+38h+arg_18]; void *
0x1800086ef  test    rcx, rcx
0x1800086f2  jz      short loc_1800086F9
0x1800086f4  call    MIDL_user_free
0x1800086f9  mov     eax, edi
0x1800086fb  jmp     short loc_180008701
0x1800086fd  mov     eax, dword ptr [rsp+38h+arg_8]
0x180008701  mov     rbx, [rsp+38h+arg_10]
0x180008706  add     rsp, 30h
0x18000870a  pop     rdi
0x18000870b  retn
0x18000870c  mov     r9d, 80004003h; char *
0x180008712  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008719  mov     edx, 10h; void *
0x18000871e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

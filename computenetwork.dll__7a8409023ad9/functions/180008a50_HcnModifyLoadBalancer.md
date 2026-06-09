# HcnModifyLoadBalancer

- ea: `0x180008a50`
- end: `0x180008b01`
- name: `HcnModifyLoadBalancer`
- size: `177`
- prototype: `HRESULT __stdcall(HCN_LOADBALANCER LoadBalancer, PCWSTR Settings, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002254`
- `0x180007904`
- `0x180008a50`
- `0x180009d10`

## string_xrefs

- `0x180008aeb`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnModifyLoadBalancer(HCN_LOADBALANCER LoadBalancer, PCWSTR Settings, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HCN_LOADBALANCER v12; // [rsp+40h] [rbp+8h] BYREF
  PCWSTR v13; // [rsp+48h] [rbp+10h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = Settings;
  v12 = LoadBalancer;
  try
  {
    if ( !LoadBalancer )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x414,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v10[0]);
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *),void * &,unsigned short const * &,unsigned short * *>(
           HnsRpc_ModifyLoadBalancer,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x421, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008a50  mov     [rsp+arg_10], rbx
0x180008a55  mov     [rsp+arg_8], rdx
0x180008a5a  mov     [rsp+arg_0], rcx
0x180008a5f  push    rdi
0x180008a60  sub     rsp, 30h
0x180008a64  mov     rbx, r8
0x180008a67  mov     rax, [rsp+38h]
0x180008a6c  test    rcx, rcx
0x180008a6f  jz      short loc_180008AE5
0x180008a71  test    rbx, rbx
0x180008a74  jz      short loc_180008A7D
0x180008a76  mov     qword ptr [r8], 0
0x180008a7d  mov     [rsp+38h+arg_18], 0
0x180008a86  lea     rax, [rsp+38h+arg_18]
0x180008a8b  mov     [rsp+38h+var_18], rax
0x180008a90  lea     r9, [rsp+38h+var_18]
0x180008a95  lea     r8, [rsp+38h+arg_8]
0x180008a9a  lea     rdx, [rsp+38h+arg_0]
0x180008a9f  lea     rcx, HnsRpc_ModifyLoadBalancer
0x180008aa6  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z
0x180008aab  mov     edi, eax
0x180008aad  test    rbx, rbx
0x180008ab0  jz      short loc_180008AC3
0x180008ab2  mov     rdx, [rsp+38h+arg_18]
0x180008ab7  xor     ecx, ecx
0x180008ab9  mov     [rsp+38h+arg_18], rcx
0x180008abe  mov     [rbx], rdx
0x180008ac1  jmp     short loc_180008AC8
0x180008ac3  mov     rcx, [rsp+38h+arg_18]; void *
0x180008ac8  test    rcx, rcx
0x180008acb  jz      short loc_180008AD2
0x180008acd  call    MIDL_user_free
0x180008ad2  mov     eax, edi
0x180008ad4  jmp     short loc_180008ADA
0x180008ad6  mov     eax, dword ptr [rsp+38h+arg_0]
0x180008ada  mov     rbx, [rsp+38h+arg_10]
0x180008adf  add     rsp, 30h
0x180008ae3  pop     rdi
0x180008ae4  retn
0x180008ae5  mov     r9d, 80070057h; char *
0x180008aeb  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008af2  mov     edx, 414h; void *
0x180008af7  mov     rcx, rax; this
0x180008afa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

# HcnEnumerateNetworks

- ea: `0x1800087f0`
- end: `0x1800088a5`
- name: `HcnEnumerateNetworks`
- size: `181`
- prototype: `HRESULT __stdcall(PCWSTR Query, PWSTR *Networks, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f88`
- `0x180007904`
- `0x1800087f0`
- `0x180009d10`

## string_xrefs

- `0x180008892`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnEnumerateNetworks(PCWSTR Query, PWSTR *Networks, PWSTR *ErrorRecord)
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

  v13 = Networks;
  v12 = Query;
  try
  {
    if ( !Networks )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v10[0]);
    *Networks = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),unsigned short const * &,unsigned short * * &,unsigned short * *>(
           HnsRpc_EnumerateNetworks,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x50, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800087f0  mov     [rsp+arg_10], rbx
0x1800087f5  mov     [rsp+arg_8], rdx
0x1800087fa  mov     [rsp+arg_0], rcx
0x1800087ff  push    rdi
0x180008800  sub     rsp, 30h
0x180008804  mov     rbx, r8
0x180008807  mov     rcx, [rsp+38h]; this
0x18000880c  test    rdx, rdx
0x18000880f  jz      short loc_18000888C
0x180008811  mov     qword ptr [rdx], 0
0x180008818  test    rbx, rbx
0x18000881b  jz      short loc_180008824
0x18000881d  mov     qword ptr [r8], 0
0x180008824  mov     [rsp+38h+arg_18], 0
0x18000882d  lea     rax, [rsp+38h+arg_18]
0x180008832  mov     [rsp+38h+var_18], rax
0x180008837  lea     r9, [rsp+38h+var_18]
0x18000883c  lea     r8, [rsp+38h+arg_8]
0x180008841  lea     rdx, [rsp+38h+arg_0]
0x180008846  lea     rcx, HnsRpc_EnumerateNetworks
0x18000884d  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180008852  mov     edi, eax
0x180008854  test    rbx, rbx
0x180008857  jz      short loc_18000886A
0x180008859  mov     rdx, [rsp+38h+arg_18]
0x18000885e  xor     ecx, ecx
0x180008860  mov     [rsp+38h+arg_18], rcx
0x180008865  mov     [rbx], rdx
0x180008868  jmp     short loc_18000886F
0x18000886a  mov     rcx, [rsp+38h+arg_18]; void *
0x18000886f  test    rcx, rcx
0x180008872  jz      short loc_180008879
0x180008874  call    MIDL_user_free
0x180008879  mov     eax, edi
0x18000887b  jmp     short loc_180008881
0x18000887d  mov     eax, dword ptr [rsp+38h+arg_8]
0x180008881  mov     rbx, [rsp+38h+arg_10]
0x180008886  add     rsp, 30h
0x18000888a  pop     rdi
0x18000888b  retn
0x18000888c  mov     r9d, 80004003h; char *
0x180008892  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008899  mov     edx, 10h; void *
0x18000889e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

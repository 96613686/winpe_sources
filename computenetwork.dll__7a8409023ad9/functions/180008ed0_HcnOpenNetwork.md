# HcnOpenNetwork

- ea: `0x180008ed0`
- end: `0x180008f81`
- name: `HcnOpenNetwork`
- size: `177`
- prototype: `HRESULT __stdcall(const GUID *const Id, PHCN_NETWORK Network, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002ad4`
- `0x180007904`
- `0x180008ed0`
- `0x180009d10`

## string_xrefs

- `0x180008f6e`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnOpenNetwork(const GUID *const Id, PHCN_NETWORK Network, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PHCN_NETWORK v12; // [rsp+48h] [rbp+10h] BYREF
  void *v13; // [rsp+58h] [rbp+20h] BYREF

  v12 = Network;
  try
  {
    if ( !Network )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v10[0]);
    *Network = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v13 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,void * *,unsigned short * *),_GUID const &,void * * &,unsigned short * *>(
           HnsRpc_OpenNetwork,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x9D, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008ed0  mov     [rsp+arg_0], rbx
0x180008ed5  mov     [rsp+arg_8], rdx
0x180008eda  push    rdi
0x180008edb  sub     rsp, 30h
0x180008edf  mov     rbx, r8
0x180008ee2  mov     rax, rcx
0x180008ee5  mov     rcx, [rsp+38h]; this
0x180008eea  test    rdx, rdx
0x180008eed  jz      short loc_180008F68
0x180008eef  mov     qword ptr [rdx], 0
0x180008ef6  test    rbx, rbx
0x180008ef9  jz      short loc_180008F02
0x180008efb  mov     qword ptr [r8], 0
0x180008f02  mov     [rsp+38h+arg_18], 0
0x180008f0b  lea     rcx, [rsp+38h+arg_18]
0x180008f10  mov     [rsp+38h+var_18], rcx
0x180008f15  lea     r9, [rsp+38h+var_18]
0x180008f1a  lea     r8, [rsp+38h+arg_8]
0x180008f1f  mov     rdx, rax
0x180008f22  lea     rcx, HnsRpc_OpenNetwork
0x180008f29  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@ZAEBU1@AEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@Z1AEAPEAPEAX$$QEAPEAPEAG@Z
0x180008f2e  mov     edi, eax
0x180008f30  test    rbx, rbx
0x180008f33  jz      short loc_180008F46
0x180008f35  mov     rdx, [rsp+38h+arg_18]
0x180008f3a  xor     ecx, ecx
0x180008f3c  mov     [rsp+38h+arg_18], rcx
0x180008f41  mov     [rbx], rdx
0x180008f44  jmp     short loc_180008F4B
0x180008f46  mov     rcx, [rsp+38h+arg_18]; void *
0x180008f4b  test    rcx, rcx
0x180008f4e  jz      short loc_180008F55
0x180008f50  call    MIDL_user_free
0x180008f55  mov     eax, edi
0x180008f57  jmp     short loc_180008F5D
0x180008f59  mov     eax, dword ptr [rsp+38h+arg_8]
0x180008f5d  mov     rbx, [rsp+38h+arg_0]
0x180008f62  add     rsp, 30h
0x180008f66  pop     rdi
0x180008f67  retn
0x180008f68  mov     r9d, 80004003h; char *
0x180008f6e  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008f75  mov     edx, 10h; void *
0x180008f7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

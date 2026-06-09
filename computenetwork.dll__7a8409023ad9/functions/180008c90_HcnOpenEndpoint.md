# HcnOpenEndpoint

- ea: `0x180008c90`
- end: `0x180008d41`
- name: `HcnOpenEndpoint`
- size: `177`
- prototype: `HRESULT __stdcall(const GUID *const Id, PHCN_ENDPOINT Endpoint, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002ad4`
- `0x180007904`
- `0x180008c90`
- `0x180009d10`

## string_xrefs

- `0x180008d2e`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnOpenEndpoint(const GUID *const Id, PHCN_ENDPOINT Endpoint, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PHCN_ENDPOINT v12; // [rsp+48h] [rbp+10h] BYREF
  void *v13; // [rsp+58h] [rbp+20h] BYREF

  v12 = Endpoint;
  try
  {
    if ( !Endpoint )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v10[0]);
    *Endpoint = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v13 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,void * *,unsigned short * *),_GUID const &,void * * &,unsigned short * *>(
           HnsRpc_OpenEndpoint,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x2A4, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008c90  mov     [rsp+arg_0], rbx
0x180008c95  mov     [rsp+arg_8], rdx
0x180008c9a  push    rdi
0x180008c9b  sub     rsp, 30h
0x180008c9f  mov     rbx, r8
0x180008ca2  mov     rax, rcx
0x180008ca5  mov     rcx, [rsp+38h]; this
0x180008caa  test    rdx, rdx
0x180008cad  jz      short loc_180008D28
0x180008caf  mov     qword ptr [rdx], 0
0x180008cb6  test    rbx, rbx
0x180008cb9  jz      short loc_180008CC2
0x180008cbb  mov     qword ptr [r8], 0
0x180008cc2  mov     [rsp+38h+arg_18], 0
0x180008ccb  lea     rcx, [rsp+38h+arg_18]
0x180008cd0  mov     [rsp+38h+var_18], rcx
0x180008cd5  lea     r9, [rsp+38h+var_18]
0x180008cda  lea     r8, [rsp+38h+arg_8]
0x180008cdf  mov     rdx, rax
0x180008ce2  lea     rcx, HnsRpc_OpenEndpoint
0x180008ce9  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@ZAEBU1@AEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@Z1AEAPEAPEAX$$QEAPEAPEAG@Z
0x180008cee  mov     edi, eax
0x180008cf0  test    rbx, rbx
0x180008cf3  jz      short loc_180008D06
0x180008cf5  mov     rdx, [rsp+38h+arg_18]
0x180008cfa  xor     ecx, ecx
0x180008cfc  mov     [rsp+38h+arg_18], rcx
0x180008d01  mov     [rbx], rdx
0x180008d04  jmp     short loc_180008D0B
0x180008d06  mov     rcx, [rsp+38h+arg_18]; void *
0x180008d0b  test    rcx, rcx
0x180008d0e  jz      short loc_180008D15
0x180008d10  call    MIDL_user_free
0x180008d15  mov     eax, edi
0x180008d17  jmp     short loc_180008D1D
0x180008d19  mov     eax, dword ptr [rsp+38h+arg_8]
0x180008d1d  mov     rbx, [rsp+38h+arg_0]
0x180008d22  add     rsp, 30h
0x180008d26  pop     rdi
0x180008d27  retn
0x180008d28  mov     r9d, 80004003h; char *
0x180008d2e  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008d35  mov     edx, 10h; void *
0x180008d3a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

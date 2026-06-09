# HcnOpenNamespace

- ea: `0x180008e10`
- end: `0x180008ec1`
- name: `HcnOpenNamespace`
- size: `177`
- prototype: `HRESULT __stdcall(const GUID *const Id, PHCN_NAMESPACE Namespace, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002ad4`
- `0x180007904`
- `0x180008e10`
- `0x180009d10`

## string_xrefs

- `0x180008eae`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnOpenNamespace(const GUID *const Id, PHCN_NAMESPACE Namespace, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PHCN_NAMESPACE v12; // [rsp+48h] [rbp+10h] BYREF
  void *v13; // [rsp+58h] [rbp+20h] BYREF

  v12 = Namespace;
  try
  {
    if ( !Namespace )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v10[0]);
    *Namespace = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v13 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,void * *,unsigned short * *),_GUID const &,void * * &,unsigned short * *>(
           HnsRpc_OpenNamespace,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x19F, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008e10  mov     [rsp+arg_0], rbx
0x180008e15  mov     [rsp+arg_8], rdx
0x180008e1a  push    rdi
0x180008e1b  sub     rsp, 30h
0x180008e1f  mov     rbx, r8
0x180008e22  mov     rax, rcx
0x180008e25  mov     rcx, [rsp+38h]; this
0x180008e2a  test    rdx, rdx
0x180008e2d  jz      short loc_180008EA8
0x180008e2f  mov     qword ptr [rdx], 0
0x180008e36  test    rbx, rbx
0x180008e39  jz      short loc_180008E42
0x180008e3b  mov     qword ptr [r8], 0
0x180008e42  mov     [rsp+38h+arg_18], 0
0x180008e4b  lea     rcx, [rsp+38h+arg_18]
0x180008e50  mov     [rsp+38h+var_18], rcx
0x180008e55  lea     r9, [rsp+38h+var_18]
0x180008e5a  lea     r8, [rsp+38h+arg_8]
0x180008e5f  mov     rdx, rax
0x180008e62  lea     rcx, HnsRpc_OpenNamespace
0x180008e69  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@ZAEBU1@AEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@Z1AEAPEAPEAX$$QEAPEAPEAG@Z
0x180008e6e  mov     edi, eax
0x180008e70  test    rbx, rbx
0x180008e73  jz      short loc_180008E86
0x180008e75  mov     rdx, [rsp+38h+arg_18]
0x180008e7a  xor     ecx, ecx
0x180008e7c  mov     [rsp+38h+arg_18], rcx
0x180008e81  mov     [rbx], rdx
0x180008e84  jmp     short loc_180008E8B
0x180008e86  mov     rcx, [rsp+38h+arg_18]; void *
0x180008e8b  test    rcx, rcx
0x180008e8e  jz      short loc_180008E95
0x180008e90  call    MIDL_user_free
0x180008e95  mov     eax, edi
0x180008e97  jmp     short loc_180008E9D
0x180008e99  mov     eax, dword ptr [rsp+38h+arg_8]
0x180008e9d  mov     rbx, [rsp+38h+arg_0]
0x180008ea2  add     rsp, 30h
0x180008ea6  pop     rdi
0x180008ea7  retn
0x180008ea8  mov     r9d, 80004003h; char *
0x180008eae  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008eb5  mov     edx, 10h; void *
0x180008eba  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

# HcnModifyNamespace

- ea: `0x180008b10`
- end: `0x180008bc1`
- name: `HcnModifyNamespace`
- size: `177`
- prototype: `HRESULT __stdcall(HCN_NAMESPACE Namespace, PCWSTR Settings, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002254`
- `0x180007904`
- `0x180008b10`
- `0x180009d10`

## string_xrefs

- `0x180008bab`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnModifyNamespace(HCN_NAMESPACE Namespace, PCWSTR Settings, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HCN_NAMESPACE v12; // [rsp+40h] [rbp+8h] BYREF
  PCWSTR v13; // [rsp+48h] [rbp+10h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = Settings;
  v12 = Namespace;
  try
  {
    if ( !Namespace )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v10[0]);
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *),void * &,unsigned short const * &,unsigned short * *>(
           HnsRpc_ModifyNamespace,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x1C4, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008b10  mov     [rsp+arg_10], rbx
0x180008b15  mov     [rsp+arg_8], rdx
0x180008b1a  mov     [rsp+arg_0], rcx
0x180008b1f  push    rdi
0x180008b20  sub     rsp, 30h
0x180008b24  mov     rbx, r8
0x180008b27  mov     rax, [rsp+38h]
0x180008b2c  test    rcx, rcx
0x180008b2f  jz      short loc_180008BA5
0x180008b31  test    rbx, rbx
0x180008b34  jz      short loc_180008B3D
0x180008b36  mov     qword ptr [r8], 0
0x180008b3d  mov     [rsp+38h+arg_18], 0
0x180008b46  lea     rax, [rsp+38h+arg_18]
0x180008b4b  mov     [rsp+38h+var_18], rax
0x180008b50  lea     r9, [rsp+38h+var_18]
0x180008b55  lea     r8, [rsp+38h+arg_8]
0x180008b5a  lea     rdx, [rsp+38h+arg_0]
0x180008b5f  lea     rcx, HnsRpc_ModifyNamespace
0x180008b66  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z
0x180008b6b  mov     edi, eax
0x180008b6d  test    rbx, rbx
0x180008b70  jz      short loc_180008B83
0x180008b72  mov     rdx, [rsp+38h+arg_18]
0x180008b77  xor     ecx, ecx
0x180008b79  mov     [rsp+38h+arg_18], rcx
0x180008b7e  mov     [rbx], rdx
0x180008b81  jmp     short loc_180008B88
0x180008b83  mov     rcx, [rsp+38h+arg_18]; void *
0x180008b88  test    rcx, rcx
0x180008b8b  jz      short loc_180008B92
0x180008b8d  call    MIDL_user_free
0x180008b92  mov     eax, edi
0x180008b94  jmp     short loc_180008B9A
0x180008b96  mov     eax, dword ptr [rsp+38h+arg_0]
0x180008b9a  mov     rbx, [rsp+38h+arg_10]
0x180008b9f  add     rsp, 30h
0x180008ba3  pop     rdi
0x180008ba4  retn
0x180008ba5  mov     r9d, 80070057h; char *
0x180008bab  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008bb2  mov     edx, 1B7h; void *
0x180008bb7  mov     rcx, rax; this
0x180008bba  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

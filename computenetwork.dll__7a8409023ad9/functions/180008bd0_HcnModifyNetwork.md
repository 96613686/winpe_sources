# HcnModifyNetwork

- ea: `0x180008bd0`
- end: `0x180008c81`
- name: `HcnModifyNetwork`
- size: `177`
- prototype: `HRESULT __stdcall(HCN_NETWORK Network, PCWSTR Settings, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002254`
- `0x180007904`
- `0x180008bd0`
- `0x180009d10`

## string_xrefs

- `0x180008c6b`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnModifyNetwork(HCN_NETWORK Network, PCWSTR Settings, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HCN_NETWORK v12; // [rsp+40h] [rbp+8h] BYREF
  PCWSTR v13; // [rsp+48h] [rbp+10h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = Settings;
  v12 = Network;
  try
  {
    if ( !Network )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v10[0]);
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *),void * &,unsigned short const * &,unsigned short * *>(
           HnsRpc_ModifyNetwork,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xC2, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008bd0  mov     [rsp+arg_10], rbx
0x180008bd5  mov     [rsp+arg_8], rdx
0x180008bda  mov     [rsp+arg_0], rcx
0x180008bdf  push    rdi
0x180008be0  sub     rsp, 30h
0x180008be4  mov     rbx, r8
0x180008be7  mov     rax, [rsp+38h]
0x180008bec  test    rcx, rcx
0x180008bef  jz      short loc_180008C65
0x180008bf1  test    rbx, rbx
0x180008bf4  jz      short loc_180008BFD
0x180008bf6  mov     qword ptr [r8], 0
0x180008bfd  mov     [rsp+38h+arg_18], 0
0x180008c06  lea     rax, [rsp+38h+arg_18]
0x180008c0b  mov     [rsp+38h+var_18], rax
0x180008c10  lea     r9, [rsp+38h+var_18]
0x180008c15  lea     r8, [rsp+38h+arg_8]
0x180008c1a  lea     rdx, [rsp+38h+arg_0]
0x180008c1f  lea     rcx, HnsRpc_ModifyNetwork
0x180008c26  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z
0x180008c2b  mov     edi, eax
0x180008c2d  test    rbx, rbx
0x180008c30  jz      short loc_180008C43
0x180008c32  mov     rdx, [rsp+38h+arg_18]
0x180008c37  xor     ecx, ecx
0x180008c39  mov     [rsp+38h+arg_18], rcx
0x180008c3e  mov     [rbx], rdx
0x180008c41  jmp     short loc_180008C48
0x180008c43  mov     rcx, [rsp+38h+arg_18]; void *
0x180008c48  test    rcx, rcx
0x180008c4b  jz      short loc_180008C52
0x180008c4d  call    MIDL_user_free
0x180008c52  mov     eax, edi
0x180008c54  jmp     short loc_180008C5A
0x180008c56  mov     eax, dword ptr [rsp+38h+arg_0]
0x180008c5a  mov     rbx, [rsp+38h+arg_10]
0x180008c5f  add     rsp, 30h
0x180008c63  pop     rdi
0x180008c64  retn
0x180008c65  mov     r9d, 80070057h; char *
0x180008c6b  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008c72  mov     edx, 0B5h; void *
0x180008c77  mov     rcx, rax; this
0x180008c7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

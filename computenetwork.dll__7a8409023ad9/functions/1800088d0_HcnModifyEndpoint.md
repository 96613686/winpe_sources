# HcnModifyEndpoint

- ea: `0x1800088d0`
- end: `0x180008981`
- name: `HcnModifyEndpoint`
- size: `177`
- prototype: `HRESULT __stdcall(HCN_ENDPOINT Endpoint, PCWSTR Settings, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002254`
- `0x180007904`
- `0x1800088d0`
- `0x180009d10`

## string_xrefs

- `0x18000896b`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnModifyEndpoint(HCN_ENDPOINT Endpoint, PCWSTR Settings, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HCN_ENDPOINT v12; // [rsp+40h] [rbp+8h] BYREF
  PCWSTR v13; // [rsp+48h] [rbp+10h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = Settings;
  v12 = Endpoint;
  try
  {
    if ( !Endpoint )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2BC,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v10[0]);
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *),void * &,unsigned short const * &,unsigned short * *>(
           HnsRpc_ModifyEndpoint,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x2C9, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800088d0  mov     [rsp+arg_10], rbx
0x1800088d5  mov     [rsp+arg_8], rdx
0x1800088da  mov     [rsp+arg_0], rcx
0x1800088df  push    rdi
0x1800088e0  sub     rsp, 30h
0x1800088e4  mov     rbx, r8
0x1800088e7  mov     rax, [rsp+38h]
0x1800088ec  test    rcx, rcx
0x1800088ef  jz      short loc_180008965
0x1800088f1  test    rbx, rbx
0x1800088f4  jz      short loc_1800088FD
0x1800088f6  mov     qword ptr [r8], 0
0x1800088fd  mov     [rsp+38h+arg_18], 0
0x180008906  lea     rax, [rsp+38h+arg_18]
0x18000890b  mov     [rsp+38h+var_18], rax
0x180008910  lea     r9, [rsp+38h+var_18]
0x180008915  lea     r8, [rsp+38h+arg_8]
0x18000891a  lea     rdx, [rsp+38h+arg_0]
0x18000891f  lea     rcx, HnsRpc_ModifyEndpoint
0x180008926  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z
0x18000892b  mov     edi, eax
0x18000892d  test    rbx, rbx
0x180008930  jz      short loc_180008943
0x180008932  mov     rdx, [rsp+38h+arg_18]
0x180008937  xor     ecx, ecx
0x180008939  mov     [rsp+38h+arg_18], rcx
0x18000893e  mov     [rbx], rdx
0x180008941  jmp     short loc_180008948
0x180008943  mov     rcx, [rsp+38h+arg_18]; void *
0x180008948  test    rcx, rcx
0x18000894b  jz      short loc_180008952
0x18000894d  call    MIDL_user_free
0x180008952  mov     eax, edi
0x180008954  jmp     short loc_18000895A
0x180008956  mov     eax, dword ptr [rsp+38h+arg_0]
0x18000895a  mov     rbx, [rsp+38h+arg_10]
0x18000895f  add     rsp, 30h
0x180008963  pop     rdi
0x180008964  retn
0x180008965  mov     r9d, 80070057h; char *
0x18000896b  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008972  mov     edx, 2BCh; void *
0x180008977  mov     rcx, rax; this
0x18000897a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

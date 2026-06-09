# HcnDeleteEndpoint

- ea: `0x1800081d0`
- end: `0x18000824b`
- name: `HcnDeleteEndpoint`
- size: `123`
- prototype: `HRESULT __stdcall(const GUID *const Id, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002978`
- `0x1800081d0`
- `0x180009d10`

## pseudocode

```c
HRESULT __stdcall HcnDeleteEndpoint(const GUID *const Id, PWSTR *ErrorRecord)
{
  HRESULT v3; // edi
  unsigned int v4; // r8d
  const char *v5; // r9
  WCHAR *v6; // rdx
  void *v7; // rcx
  HRESULT result; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v10; // [rsp+38h] [rbp+10h] BYREF
  void **v11; // [rsp+40h] [rbp+18h]

  if ( ErrorRecord )
    *ErrorRecord = 0;
  v10 = 0;
  v11 = &v10;
  try
  {
    v3 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short * *),_GUID const &,unsigned short * *>();
    if ( ErrorRecord )
    {
      v6 = (WCHAR *)v10;
      v7 = 0;
      v10 = 0;
      *ErrorRecord = v6;
    }
    else
    {
      v7 = v10;
    }
    if ( v7 )
      MIDL_user_free(v7);
    result = v3;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x36B, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x1800081d0  mov     [rsp+arg_0], rbx
0x1800081d5  push    rdi
0x1800081d6  sub     rsp, 20h
0x1800081da  mov     rbx, rdx
0x1800081dd  test    rdx, rdx
0x1800081e0  jz      short loc_1800081E9
0x1800081e2  mov     qword ptr [rdx], 0
0x1800081e9  mov     [rsp+28h+arg_8], 0
0x1800081f2  lea     rax, [rsp+28h+arg_8]
0x1800081f7  mov     [rsp+28h+arg_10], rax
0x1800081fc  lea     r8, [rsp+28h+arg_10]
0x180008201  mov     rdx, rcx
0x180008204  lea     rcx, HnsRpc_DeleteEndpoint
0x18000820b  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAG@ZAEBU1@PEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAG@Z1$$QEAPEAPEAG@Z
0x180008210  mov     edi, eax
0x180008212  test    rbx, rbx
0x180008215  jz      short loc_180008228
0x180008217  mov     rdx, [rsp+28h+arg_8]
0x18000821c  xor     ecx, ecx
0x18000821e  mov     [rsp+28h+arg_8], rcx
0x180008223  mov     [rbx], rdx
0x180008226  jmp     short loc_18000822D
0x180008228  mov     rcx, [rsp+28h+arg_8]; void *
0x18000822d  test    rcx, rcx
0x180008230  jz      short loc_180008237
0x180008232  call    MIDL_user_free
0x180008237  mov     eax, edi
0x180008239  jmp     short loc_18000823F
0x18000823b  mov     eax, dword ptr [rsp+28h+arg_8]
0x18000823f  mov     rbx, [rsp+28h+arg_0]
0x180008244  add     rsp, 20h
0x180008248  pop     rdi
0x180008249  retn
```

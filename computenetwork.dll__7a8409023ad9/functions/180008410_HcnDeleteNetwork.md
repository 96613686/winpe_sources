# HcnDeleteNetwork

- ea: `0x180008410`
- end: `0x18000848b`
- name: `HcnDeleteNetwork`
- size: `123`
- prototype: `HRESULT __stdcall(const GUID *const Id, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002978`
- `0x180008410`
- `0x180009d10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnDeleteNetwork(const GUID *const Id, PWSTR *ErrorRecord)
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x10E, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180008410  mov     [rsp+arg_0], rbx
0x180008415  push    rdi
0x180008416  sub     rsp, 20h
0x18000841a  mov     rbx, rdx
0x18000841d  test    rdx, rdx
0x180008420  jz      short loc_180008429
0x180008422  mov     qword ptr [rdx], 0
0x180008429  mov     [rsp+28h+arg_8], 0
0x180008432  lea     rax, [rsp+28h+arg_8]
0x180008437  mov     [rsp+28h+arg_10], rax
0x18000843c  lea     r8, [rsp+28h+arg_10]
0x180008441  mov     rdx, rcx
0x180008444  lea     rcx, HnsRpc_DeleteNetwork
0x18000844b  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAG@ZAEBU1@PEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAG@Z1$$QEAPEAPEAG@Z
0x180008450  mov     edi, eax
0x180008452  test    rbx, rbx
0x180008455  jz      short loc_180008468
0x180008457  mov     rdx, [rsp+28h+arg_8]
0x18000845c  xor     ecx, ecx
0x18000845e  mov     [rsp+28h+arg_8], rcx
0x180008463  mov     [rbx], rdx
0x180008466  jmp     short loc_18000846D
0x180008468  mov     rcx, [rsp+28h+arg_8]; void *
0x18000846d  test    rcx, rcx
0x180008470  jz      short loc_180008477
0x180008472  call    MIDL_user_free
0x180008477  mov     eax, edi
0x180008479  jmp     short loc_18000847F
0x18000847b  mov     eax, dword ptr [rsp+28h+arg_8]
0x18000847f  mov     rbx, [rsp+28h+arg_0]
0x180008484  add     rsp, 20h
0x180008488  pop     rdi
0x180008489  retn
```

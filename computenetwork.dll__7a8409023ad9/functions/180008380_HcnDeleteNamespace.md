# HcnDeleteNamespace

- ea: `0x180008380`
- end: `0x1800083fb`
- name: `HcnDeleteNamespace`
- size: `123`
- prototype: `HRESULT __stdcall(const GUID *const Id, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002978`
- `0x180008380`
- `0x180009d10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnDeleteNamespace(const GUID *const Id, PWSTR *ErrorRecord)
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x210, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180008380  mov     [rsp+arg_0], rbx
0x180008385  push    rdi
0x180008386  sub     rsp, 20h
0x18000838a  mov     rbx, rdx
0x18000838d  test    rdx, rdx
0x180008390  jz      short loc_180008399
0x180008392  mov     qword ptr [rdx], 0
0x180008399  mov     [rsp+28h+arg_8], 0
0x1800083a2  lea     rax, [rsp+28h+arg_8]
0x1800083a7  mov     [rsp+28h+arg_10], rax
0x1800083ac  lea     r8, [rsp+28h+arg_10]
0x1800083b1  mov     rdx, rcx
0x1800083b4  lea     rcx, HnsRpc_DeleteNamespace
0x1800083bb  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAG@ZAEBU1@PEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAG@Z1$$QEAPEAPEAG@Z
0x1800083c0  mov     edi, eax
0x1800083c2  test    rbx, rbx
0x1800083c5  jz      short loc_1800083D8
0x1800083c7  mov     rdx, [rsp+28h+arg_8]
0x1800083cc  xor     ecx, ecx
0x1800083ce  mov     [rsp+28h+arg_8], rcx
0x1800083d3  mov     [rbx], rdx
0x1800083d6  jmp     short loc_1800083DD
0x1800083d8  mov     rcx, [rsp+28h+arg_8]; void *
0x1800083dd  test    rcx, rcx
0x1800083e0  jz      short loc_1800083E7
0x1800083e2  call    MIDL_user_free
0x1800083e7  mov     eax, edi
0x1800083e9  jmp     short loc_1800083EF
0x1800083eb  mov     eax, dword ptr [rsp+28h+arg_8]
0x1800083ef  mov     rbx, [rsp+28h+arg_0]
0x1800083f4  add     rsp, 20h
0x1800083f8  pop     rdi
0x1800083f9  retn
```

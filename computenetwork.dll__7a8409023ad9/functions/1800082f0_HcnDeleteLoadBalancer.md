# HcnDeleteLoadBalancer

- ea: `0x1800082f0`
- end: `0x18000836b`
- name: `HcnDeleteLoadBalancer`
- size: `123`
- prototype: `HRESULT __stdcall(const GUID *const Id, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002978`
- `0x1800082f0`
- `0x180009d10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnDeleteLoadBalancer(const GUID *const Id, PWSTR *ErrorRecord)
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x46D, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x1800082f0  mov     [rsp+arg_0], rbx
0x1800082f5  push    rdi
0x1800082f6  sub     rsp, 20h
0x1800082fa  mov     rbx, rdx
0x1800082fd  test    rdx, rdx
0x180008300  jz      short loc_180008309
0x180008302  mov     qword ptr [rdx], 0
0x180008309  mov     [rsp+28h+arg_8], 0
0x180008312  lea     rax, [rsp+28h+arg_8]
0x180008317  mov     [rsp+28h+arg_10], rax
0x18000831c  lea     r8, [rsp+28h+arg_10]
0x180008321  mov     rdx, rcx
0x180008324  lea     rcx, HnsRpc_DeleteLoadBalancer
0x18000832b  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAG@ZAEBU1@PEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAG@Z1$$QEAPEAPEAG@Z
0x180008330  mov     edi, eax
0x180008332  test    rbx, rbx
0x180008335  jz      short loc_180008348
0x180008337  mov     rdx, [rsp+28h+arg_8]
0x18000833c  xor     ecx, ecx
0x18000833e  mov     [rsp+28h+arg_8], rcx
0x180008343  mov     [rbx], rdx
0x180008346  jmp     short loc_18000834D
0x180008348  mov     rcx, [rsp+28h+arg_8]; void *
0x18000834d  test    rcx, rcx
0x180008350  jz      short loc_180008357
0x180008352  call    MIDL_user_free
0x180008357  mov     eax, edi
0x180008359  jmp     short loc_18000835F
0x18000835b  mov     eax, dword ptr [rsp+28h+arg_8]
0x18000835f  mov     rbx, [rsp+28h+arg_0]
0x180008364  add     rsp, 20h
0x180008368  pop     rdi
0x180008369  retn
```

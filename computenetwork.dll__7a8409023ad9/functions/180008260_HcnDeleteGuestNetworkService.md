# HcnDeleteGuestNetworkService

- ea: `0x180008260`
- end: `0x1800082db`
- name: `HcnDeleteGuestNetworkService`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180002978`
- `0x180008260`
- `0x180009d10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnDeleteGuestNetworkService(__int64 a1, _QWORD *a2)
{
  unsigned int v3; // edi
  unsigned int v4; // r8d
  const char *v5; // r9
  void *v6; // rdx
  void *v7; // rcx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v10; // [rsp+38h] [rbp+10h] BYREF
  void **v11; // [rsp+40h] [rbp+18h]

  if ( a2 )
    *a2 = 0;
  v10 = 0;
  v11 = &v10;
  try
  {
    v3 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short * *),_GUID const &,unsigned short * *>();
    if ( a2 )
    {
      v6 = v10;
      v7 = 0;
      v10 = 0;
      *a2 = v6;
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x666, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180008260  mov     [rsp+arg_0], rbx
0x180008265  push    rdi
0x180008266  sub     rsp, 20h
0x18000826a  mov     rbx, rdx
0x18000826d  test    rdx, rdx
0x180008270  jz      short loc_180008279
0x180008272  mov     qword ptr [rdx], 0
0x180008279  mov     [rsp+28h+arg_8], 0
0x180008282  lea     rax, [rsp+28h+arg_8]
0x180008287  mov     [rsp+28h+arg_10], rax
0x18000828c  lea     r8, [rsp+28h+arg_10]
0x180008291  mov     rdx, rcx
0x180008294  lea     rcx, HnsRpc_DeleteGuestNetworkService
0x18000829b  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAG@ZAEBU1@PEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAG@Z1$$QEAPEAPEAG@Z
0x1800082a0  mov     edi, eax
0x1800082a2  test    rbx, rbx
0x1800082a5  jz      short loc_1800082B8
0x1800082a7  mov     rdx, [rsp+28h+arg_8]
0x1800082ac  xor     ecx, ecx
0x1800082ae  mov     [rsp+28h+arg_8], rcx
0x1800082b3  mov     [rbx], rdx
0x1800082b6  jmp     short loc_1800082BD
0x1800082b8  mov     rcx, [rsp+28h+arg_8]; void *
0x1800082bd  test    rcx, rcx
0x1800082c0  jz      short loc_1800082C7
0x1800082c2  call    MIDL_user_free
0x1800082c7  mov     eax, edi
0x1800082c9  jmp     short loc_1800082CF
0x1800082cb  mov     eax, dword ptr [rsp+28h+arg_8]
0x1800082cf  mov     rbx, [rsp+28h+arg_0]
0x1800082d4  add     rsp, 20h
0x1800082d8  pop     rdi
0x1800082d9  retn
```
